# BaseSrvSetTermsrvClientTimeZone

- ea: `0x180006490`
- end: `0x180006730`
- name: `BaseSrvSetTermsrvClientTimeZone`
- size: `672`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006490`
- `0x18000e010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800064db`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800064db`
- `ntdll!LdrGetDllHandle` at `0x180006690`
- `ntdll!LdrGetDllHandle` at `0x180006690`
- `ntdll!RtlInitString` at `0x1800066c4`
- `ntdll!RtlInitString` at `0x1800066c4`
- `ntdll!LdrGetProcedureAddress` at `0x1800066e7`
- `ntdll!LdrGetProcedureAddress` at `0x1800066e7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180006705`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180006705`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000dd45`
- `ntdll!RtlInitUnicodeString` at `0x180006673`
- `ntdll!RtlInitUnicodeString` at `0x180006673`
- `CSRSRV!CsrValidateMessageBuffer` at `0x1800064b3`
- `CSRSRV!CsrValidateMessageBuffer` at `0x1800064b3`

## pseudocode

```c
__int64 __fastcall BaseSrvSetTermsrvClientTimeZone(__int64 a1)
{
  _OWORD *v2; // rcx
  __int64 v3; // rdx
  _OWORD *v4; // rax
  __int64 v5; // r8
  PVOID v6; // rax
  NTSTATUS v7; // eax
  signed __int32 v9[8]; // [rsp+0h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF
  _STRING Name; // [rsp+50h] [rbp-38h] BYREF
  _DWORD v12[8]; // [rsp+60h] [rbp-28h] BYREF
  int v13; // [rsp+90h] [rbp+8h] BYREF
  PVOID DllHandle; // [rsp+A0h] [rbp+18h] BYREF

  if ( (unsigned __int8)CsrValidateMessageBuffer(a1, a1 + 64, *(unsigned int *)(a1 + 72), 1)
    && *(_DWORD *)(a1 + 72) == 432 )
  {
    RtlAcquireSRWLockExclusive(&qword_180013630);
    v13 = 0;
    Name = 0;
    DllHandle = 0;
    DestinationString = 0;
    memset(v12, 0, 28);
    *(_DWORD *)(BaseSrvpStaticServerData + 2512) |= 0x80000000;
    _InterlockedOr(v9, 0);
    v2 = *(_OWORD **)(a1 + 64);
    v3 = BaseSrvpStaticServerData;
    v4 = (_OWORD *)(BaseSrvpStaticServerData + 2060);
    v5 = 3;
    do
    {
      *v4 = *v2;
      v4[1] = v2[1];
      v4[2] = v2[2];
      v4[3] = v2[3];
      v4[4] = v2[4];
      v4[5] = v2[5];
      v4[6] = v2[6];
      v4[7] = v2[7];
      v4 += 8;
      v2 += 8;
      --v5;
    }
    while ( v5 );
    *v4 = *v2;
    v4[1] = v2[1];
    v4[2] = v2[2];
    *(_QWORD *)(v3 + 2492) = *(_QWORD *)(a1 + 76);
    *(_DWORD *)(v3 + 2500) = *(_DWORD *)(a1 + 84);
    *(_DWORD *)(v3 + 2504) = *(_DWORD *)(a1 + 88);
    *(_DWORD *)(BaseSrvpStaticServerData + 2512) = *(_DWORD *)(v3 + 2512) + 1;
    _InterlockedOr(v9, 0);
    *(_DWORD *)(BaseSrvpStaticServerData + 2512) &= ~0x80000000;
    v13 = 16;
    v12[0] = 32;
    DllHandle = 0;
    v6 = PBROADCASTSYSTEMMESSAGEEXW;
    if ( !PBROADCASTSYSTEMMESSAGEEXW )
    {
      RtlInitUnicodeString(&DestinationString, L"user32");
      v7 = LdrGetDllHandle(0, 0, &DestinationString, &DllHandle);
      if ( DllHandle )
      {
        if ( v7 >= 0 )
        {
          RtlInitString(&Name, "CsrBroadcastSystemMessageExW");
          if ( LdrGetProcedureAddress(DllHandle, &Name, 0, &PBROADCASTSYSTEMMESSAGEEXW) < 0 )
          {
            PBROADCASTSYSTEMMESSAGEEXW = 0;
            goto LABEL_13;
          }
        }
      }
      v6 = PBROADCASTSYSTEMMESSAGEEXW;
      if ( !PBROADCASTSYSTEMMESSAGEEXW )
        goto LABEL_13;
    }
    ((void (__fastcall *)(__int64, int *, __int64, _QWORD, _QWORD, _DWORD *))v6)(16, &v13, 30, 0, 0, v12);
LABEL_13:
    RtlReleaseSRWLockExclusive(&qword_180013630);
    return 0;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x180006490  mov     [rsp+arg_8], rbx
0x180006495  mov     [rsp+arg_18], rsi
0x18000649a  push    rdi
0x18000649b  sub     rsp, 80h
0x1800064a2  mov     rdi, rcx
0x1800064a5  mov     r9d, 1
0x1800064ab  mov     r8d, [rcx+48h]
0x1800064af  lea     rdx, [rcx+40h]
0x1800064b3  call    cs:__imp_CsrValidateMessageBuffer
0x1800064ba  nop     dword ptr [rax+rax+00h]
0x1800064bf  test    al, al
0x1800064c1  jz      loc_180006729
0x1800064c7  cmp     dword ptr [rdi+48h], 1B0h
0x1800064ce  jnz     loc_180006729
0x1800064d4  lea     rcx, qword_180013630
0x1800064db  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800064e2  nop     dword ptr [rax+rax+00h]
0x1800064e7  nop
0x1800064e8  xor     esi, esi
0x1800064ea  mov     [rsp+88h+arg_0], esi
0x1800064f1  xorps   xmm0, xmm0
0x1800064f4  movups  xmmword ptr [rsp+88h+Name.Length], xmm0
0x1800064f9  mov     [rsp+88h+DllHandle], rsi
0x180006501  xorps   xmm1, xmm1
0x180006504  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm1
0x180006509  xor     eax, eax
0x18000650b  mov     [rsp+88h+var_28+4], eax
0x18000650f  movups  xmmword ptr [rsp+88h+var_28], xmm0
0x180006514  movups  xmmword ptr [rsp+88h+var_28+0Ch], xmm0
0x180006519  mov     rax, cs:BaseSrvpStaticServerData
0x180006520  mov     ecx, [rax+9D0h]
0x180006526  bts     ecx, 1Fh
0x18000652a  mov     rax, cs:BaseSrvpStaticServerData
0x180006531  mov     [rax+9D0h], ecx
0x180006537  lock or [rsp+88h+var_88], esi
0x18000653b  mov     rcx, [rdi+40h]
0x18000653f  mov     rdx, cs:BaseSrvpStaticServerData
0x180006546  lea     rax, [rdx+80Ch]
0x18000654d  mov     r8d, 3
0x180006553  movups  xmm0, xmmword ptr [rcx]
0x180006556  movups  xmmword ptr [rax], xmm0
0x180006559  movups  xmm1, xmmword ptr [rcx+10h]
0x18000655d  movups  xmmword ptr [rax+10h], xmm1
0x180006561  movups  xmm0, xmmword ptr [rcx+20h]
0x180006565  movups  xmmword ptr [rax+20h], xmm0
0x180006569  movups  xmm1, xmmword ptr [rcx+30h]
0x18000656d  movups  xmmword ptr [rax+30h], xmm1
0x180006571  movups  xmm0, xmmword ptr [rcx+40h]
0x180006575  movups  xmmword ptr [rax+40h], xmm0
0x180006579  movups  xmm1, xmmword ptr [rcx+50h]
0x18000657d  movups  xmmword ptr [rax+50h], xmm1
0x180006581  movups  xmm0, xmmword ptr [rcx+60h]
0x180006585  movups  xmmword ptr [rax+60h], xmm0
0x180006589  movups  xmm1, xmmword ptr [rcx+70h]
0x18000658d  movups  xmmword ptr [rax+70h], xmm1
0x180006591  lea     rax, [rax+80h]
0x180006598  lea     rcx, [rcx+80h]
0x18000659f  sub     r8, 1
0x1800065a3  jnz     short loc_180006553
0x1800065a5  movups  xmm0, xmmword ptr [rcx]
0x1800065a8  movups  xmmword ptr [rax], xmm0
0x1800065ab  movups  xmm1, xmmword ptr [rcx+10h]
0x1800065af  movups  xmmword ptr [rax+10h], xmm1
0x1800065b3  movups  xmm0, xmmword ptr [rcx+20h]
0x1800065b7  movups  xmmword ptr [rax+20h], xmm0
0x1800065bb  movsd   xmm0, qword ptr [rdi+4Ch]
0x1800065c0  movsd   qword ptr [rdx+9BCh], xmm0
0x1800065c8  mov     eax, [rdi+54h]
0x1800065cb  mov     [rdx+9C4h], eax
0x1800065d1  mov     eax, [rdi+58h]
0x1800065d4  mov     [rdx+9C8h], eax
0x1800065da  mov     ecx, [rdx+9D0h]
0x1800065e0  inc     ecx
0x1800065e2  mov     rax, cs:BaseSrvpStaticServerData
0x1800065e9  mov     [rax+9D0h], ecx
0x1800065ef  lock or [rsp+88h+var_88], esi
0x1800065f3  mov     rax, cs:BaseSrvpStaticServerData
0x1800065fa  mov     ecx, [rax+9D0h]
0x180006600  btr     ecx, 1Fh
0x180006604  mov     rax, cs:BaseSrvpStaticServerData
0x18000660b  mov     [rax+9D0h], ecx
0x180006611  mov     [rsp+88h+arg_0], 10h
0x18000661c  mov     [rsp+88h+var_28], 20h ; ' '
0x180006624  mov     [rsp+88h+DllHandle], rsi
0x18000662c  mov     rax, cs:PBROADCASTSYSTEMMESSAGEEXW
0x180006633  test    rax, rax
0x180006636  jz      short loc_180006667
0x180006638  lea     rdx, [rsp+88h+var_28]
0x18000663d  mov     [rsp+88h+var_60], rdx
0x180006642  mov     [rsp+88h+var_68], rsi
0x180006647  xor     r9d, r9d
0x18000664a  mov     r8d, 1Eh
0x180006650  lea     rdx, [rsp+88h+arg_0]
0x180006658  mov     ecx, 10h
0x18000665d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006662  jmp     loc_1800066FE
0x180006667  lea     rdx, aUser32; "user32"
0x18000666e  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x180006673  call    cs:__imp_RtlInitUnicodeString
0x18000667a  nop     dword ptr [rax+rax+00h]
0x18000667f  lea     r9, [rsp+88h+DllHandle]; DllHandle
0x180006687  lea     r8, [rsp+88h+DestinationString]; DllName
0x18000668c  xor     edx, edx; DllCharacteristics
0x18000668e  xor     ecx, ecx; DllPath
0x180006690  call    cs:__imp_LdrGetDllHandle
0x180006697  nop     dword ptr [rax+rax+00h]
0x18000669c  cmp     [rsp+88h+DllHandle], rsi
0x1800066a4  jnz     short loc_1800066B4
0x1800066a6  mov     rax, cs:PBROADCASTSYSTEMMESSAGEEXW
0x1800066ad  test    rax, rax
0x1800066b0  jnz     short loc_180006638
0x1800066b2  jmp     short loc_1800066FE
0x1800066b4  test    eax, eax
0x1800066b6  js      short loc_1800066A6
0x1800066b8  lea     rdx, aCsrbroadcastsy; "CsrBroadcastSystemMessageExW"
0x1800066bf  lea     rcx, [rsp+88h+Name]; DestinationString
0x1800066c4  call    cs:__imp_RtlInitString
0x1800066cb  nop     dword ptr [rax+rax+00h]
0x1800066d0  lea     r9, PBROADCASTSYSTEMMESSAGEEXW; ProcedureAddress
0x1800066d7  xor     r8d, r8d; Ordinal
0x1800066da  lea     rdx, [rsp+88h+Name]; Name
0x1800066df  mov     rcx, [rsp+88h+DllHandle]; BaseAddress
0x1800066e7  call    cs:__imp_LdrGetProcedureAddress
0x1800066ee  nop     dword ptr [rax+rax+00h]
0x1800066f3  test    eax, eax
0x1800066f5  jns     short loc_1800066A6
0x1800066f7  mov     cs:PBROADCASTSYSTEMMESSAGEEXW, rsi
0x1800066fe  lea     rcx, qword_180013630
0x180006705  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000670c  nop     dword ptr [rax+rax+00h]
0x180006711  xor     eax, eax
0x180006713  lea     r11, [rsp+88h+var_8]
0x18000671b  mov     rbx, [r11+18h]
0x18000671f  mov     rsi, [r11+28h]
0x180006723  mov     rsp, r11
0x180006726  pop     rdi
0x180006727  retn
0x180006729  mov     eax, 0C000000Dh
0x18000672e  jmp     short loc_180006713
0x18000dd30  push    rbp
0x18000dd32  sub     rsp, 40h
0x18000dd36  mov     rbp, rdx
0x18000dd39  lea     rcx, qword_180013630
0x18000dd40  add     rsp, 40h
0x18000dd44  pop     rbp
0x18000dd45  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
