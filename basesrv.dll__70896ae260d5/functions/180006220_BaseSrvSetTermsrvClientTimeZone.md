# BaseSrvSetTermsrvClientTimeZone

- ea: `0x180006220`
- end: `0x1800064b5`
- name: `BaseSrvSetTermsrvClientTimeZone`
- size: `661`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180006220`
- `0x18000e010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006266`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180006266`
- `ntdll!LdrGetDllHandle` at `0x180006419`
- `ntdll!LdrGetDllHandle` at `0x180006419`
- `ntdll!RtlInitString` at `0x18000644d`
- `ntdll!RtlInitString` at `0x18000644d`
- `ntdll!LdrGetProcedureAddress` at `0x180006470`
- `ntdll!LdrGetProcedureAddress` at `0x180006470`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000648e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000648e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d935`
- `ntdll!RtlInitUnicodeString` at `0x1800063fc`
- `ntdll!RtlInitUnicodeString` at `0x1800063fc`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000623e`
- `CSRSRV!CsrValidateMessageBuffer` at `0x18000623e`

## pseudocode

```c
__int64 __fastcall BaseSrvSetTermsrvClientTimeZone(__int64 a1)
{
  __int64 v1; // rbx
  _OWORD *v2; // rcx
  __int64 v3; // rdx
  _OWORD *v4; // rax
  __int64 v5; // r8
  void (__fastcall *v6)(__int64, int *, __int64); // rax
  NTSTATUS v7; // eax
  signed __int32 v9[8]; // [rsp+0h] [rbp-88h] BYREF
  __int64 v10; // [rsp+20h] [rbp-68h]
  __int128 *v11; // [rsp+28h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF
  _STRING Name; // [rsp+50h] [rbp-38h] BYREF
  __int128 v14; // [rsp+60h] [rbp-28h] BYREF
  __int64 v15; // [rsp+70h] [rbp-18h]
  int v16; // [rsp+78h] [rbp-10h]
  int v17; // [rsp+90h] [rbp+8h] BYREF
  PVOID DllHandle; // [rsp+A0h] [rbp+18h] BYREF

  v1 = a1 + 64;
  if ( (unsigned __int8)CsrValidateMessageBuffer(a1, a1 + 64, *(unsigned int *)(a1 + 72), 1)
    && *(_DWORD *)(v1 + 8) == 432 )
  {
    RtlAcquireSRWLockExclusive(&qword_180013630);
    v17 = 0;
    Name = 0;
    DllHandle = 0;
    DestinationString = 0;
    v14 = 0;
    v15 = 0;
    v16 = 0;
    *(_DWORD *)(BaseSrvpStaticServerData + 2512) |= 0x80000000;
    _InterlockedOr(v9, 0);
    v2 = *(_OWORD **)v1;
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
      v4 += 8;
      *(v4 - 1) = v2[7];
      v2 += 8;
      --v5;
    }
    while ( v5 );
    *v4 = *v2;
    v4[1] = v2[1];
    v4[2] = v2[2];
    *(_QWORD *)(v3 + 2492) = *(_QWORD *)(v1 + 12);
    *(_DWORD *)(v3 + 2500) = *(_DWORD *)(v1 + 20);
    *(_DWORD *)(v3 + 2504) = *(_DWORD *)(v1 + 24);
    *(_DWORD *)(BaseSrvpStaticServerData + 2512) = *(_DWORD *)(v3 + 2512) + 1;
    _InterlockedOr(v9, 0);
    *(_DWORD *)(BaseSrvpStaticServerData + 2512) &= ~0x80000000;
    v17 = 16;
    LODWORD(v14) = 32;
    DllHandle = 0;
    v6 = (void (__fastcall *)(__int64, int *, __int64))PBROADCASTSYSTEMMESSAGEEXW;
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
      v6 = (void (__fastcall *)(__int64, int *, __int64))PBROADCASTSYSTEMMESSAGEEXW;
      if ( !PBROADCASTSYSTEMMESSAGEEXW )
        goto LABEL_13;
    }
    v11 = &v14;
    v10 = 0;
    v6(16, &v17, 30);
LABEL_13:
    RtlReleaseSRWLockExclusive(&qword_180013630);
    return 0;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x180006220  mov     [rsp+arg_8], rbx
0x180006225  push    rdi
0x180006226  sub     rsp, 80h
0x18000622d  lea     rbx, [rcx+40h]
0x180006231  mov     r9d, 1
0x180006237  mov     r8d, [rbx+8]
0x18000623b  mov     rdx, rbx
0x18000623e  call    cs:__imp_CsrValidateMessageBuffer
0x180006245  nop     dword ptr [rax+rax+00h]
0x18000624a  test    al, al
0x18000624c  jz      loc_1800064AE
0x180006252  cmp     dword ptr [rbx+8], 1B0h
0x180006259  jnz     loc_1800064AE
0x18000625f  lea     rcx, qword_180013630
0x180006266  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000626d  nop     dword ptr [rax+rax+00h]
0x180006272  nop
0x180006273  xor     edi, edi
0x180006275  mov     [rsp+88h+arg_0], edi
0x18000627c  xorps   xmm0, xmm0
0x18000627f  movups  xmmword ptr [rsp+88h+Name.Length], xmm0
0x180006284  mov     [rsp+88h+DllHandle], rdi
0x18000628c  xorps   xmm1, xmm1
0x18000628f  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm1
0x180006294  xor     eax, eax
0x180006296  mov     dword ptr [rsp+88h+var_28+4], eax
0x18000629a  movups  [rsp+88h+var_28], xmm0
0x18000629f  mov     [rsp+88h+var_18], rax
0x1800062a4  mov     [rsp+88h+var_10], eax
0x1800062a8  mov     rax, cs:BaseSrvpStaticServerData
0x1800062af  mov     ecx, [rax+9D0h]
0x1800062b5  bts     ecx, 1Fh
0x1800062b9  mov     rax, cs:BaseSrvpStaticServerData
0x1800062c0  mov     [rax+9D0h], ecx
0x1800062c6  lock or [rsp+88h+var_88], edi
0x1800062ca  mov     rcx, [rbx]
0x1800062cd  mov     rdx, cs:BaseSrvpStaticServerData
0x1800062d4  lea     rax, [rdx+80Ch]
0x1800062db  lea     r8d, [rdi+3]
0x1800062df  movups  xmm0, xmmword ptr [rcx]
0x1800062e2  movups  xmmword ptr [rax], xmm0
0x1800062e5  movups  xmm1, xmmword ptr [rcx+10h]
0x1800062e9  movups  xmmword ptr [rax+10h], xmm1
0x1800062ed  movups  xmm0, xmmword ptr [rcx+20h]
0x1800062f1  movups  xmmword ptr [rax+20h], xmm0
0x1800062f5  movups  xmm1, xmmword ptr [rcx+30h]
0x1800062f9  movups  xmmword ptr [rax+30h], xmm1
0x1800062fd  movups  xmm0, xmmword ptr [rcx+40h]
0x180006301  movups  xmmword ptr [rax+40h], xmm0
0x180006305  movups  xmm1, xmmword ptr [rcx+50h]
0x180006309  movups  xmmword ptr [rax+50h], xmm1
0x18000630d  movups  xmm0, xmmword ptr [rcx+60h]
0x180006311  movups  xmmword ptr [rax+60h], xmm0
0x180006315  lea     rax, [rax+80h]
0x18000631c  movups  xmm1, xmmword ptr [rcx+70h]
0x180006320  movups  xmmword ptr [rax-10h], xmm1
0x180006324  lea     rcx, [rcx+80h]
0x18000632b  sub     r8, 1
0x18000632f  jnz     short loc_1800062DF
0x180006331  movups  xmm0, xmmword ptr [rcx]
0x180006334  movups  xmmword ptr [rax], xmm0
0x180006337  movups  xmm1, xmmword ptr [rcx+10h]
0x18000633b  movups  xmmword ptr [rax+10h], xmm1
0x18000633f  movups  xmm0, xmmword ptr [rcx+20h]
0x180006343  movups  xmmword ptr [rax+20h], xmm0
0x180006347  movsd   xmm0, qword ptr [rbx+0Ch]
0x18000634c  movsd   qword ptr [rdx+9BCh], xmm0
0x180006354  mov     eax, [rbx+14h]
0x180006357  mov     [rdx+9C4h], eax
0x18000635d  mov     eax, [rbx+18h]
0x180006360  mov     [rdx+9C8h], eax
0x180006366  mov     ecx, [rdx+9D0h]
0x18000636c  inc     ecx
0x18000636e  mov     rax, cs:BaseSrvpStaticServerData
0x180006375  mov     [rax+9D0h], ecx
0x18000637b  lock or [rsp+88h+var_88], edi
0x18000637f  mov     rax, cs:BaseSrvpStaticServerData
0x180006386  mov     ecx, [rax+9D0h]
0x18000638c  btr     ecx, 1Fh
0x180006390  mov     rax, cs:BaseSrvpStaticServerData
0x180006397  mov     [rax+9D0h], ecx
0x18000639d  mov     [rsp+88h+arg_0], 10h
0x1800063a8  mov     dword ptr [rsp+88h+var_28], 20h ; ' '
0x1800063b0  mov     [rsp+88h+DllHandle], rdi
0x1800063b8  mov     rax, cs:PBROADCASTSYSTEMMESSAGEEXW
0x1800063bf  test    rax, rax
0x1800063c2  jz      short loc_1800063F0
0x1800063c4  lea     rdx, [rsp+88h+var_28]
0x1800063c9  mov     [rsp+88h+var_60], rdx
0x1800063ce  mov     [rsp+88h+var_68], rdi
0x1800063d3  xor     r9d, r9d
0x1800063d6  lea     r8d, [r9+1Eh]
0x1800063da  lea     rdx, [rsp+88h+arg_0]
0x1800063e2  lea     ecx, [r9+10h]
0x1800063e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063eb  jmp     loc_180006487
0x1800063f0  lea     rdx, aUser32; "user32"
0x1800063f7  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x1800063fc  call    cs:__imp_RtlInitUnicodeString
0x180006403  nop     dword ptr [rax+rax+00h]
0x180006408  lea     r9, [rsp+88h+DllHandle]; DllHandle
0x180006410  lea     r8, [rsp+88h+DestinationString]; DllName
0x180006415  xor     edx, edx; DllCharacteristics
0x180006417  xor     ecx, ecx; DllPath
0x180006419  call    cs:__imp_LdrGetDllHandle
0x180006420  nop     dword ptr [rax+rax+00h]
0x180006425  cmp     [rsp+88h+DllHandle], rdi
0x18000642d  jnz     short loc_18000643D
0x18000642f  mov     rax, cs:PBROADCASTSYSTEMMESSAGEEXW
0x180006436  test    rax, rax
0x180006439  jnz     short loc_1800063C4
0x18000643b  jmp     short loc_180006487
0x18000643d  test    eax, eax
0x18000643f  js      short loc_18000642F
0x180006441  lea     rdx, aCsrbroadcastsy; "CsrBroadcastSystemMessageExW"
0x180006448  lea     rcx, [rsp+88h+Name]; DestinationString
0x18000644d  call    cs:__imp_RtlInitString
0x180006454  nop     dword ptr [rax+rax+00h]
0x180006459  lea     r9, PBROADCASTSYSTEMMESSAGEEXW; ProcedureAddress
0x180006460  xor     r8d, r8d; Ordinal
0x180006463  lea     rdx, [rsp+88h+Name]; Name
0x180006468  mov     rcx, [rsp+88h+DllHandle]; BaseAddress
0x180006470  call    cs:__imp_LdrGetProcedureAddress
0x180006477  nop     dword ptr [rax+rax+00h]
0x18000647c  test    eax, eax
0x18000647e  jns     short loc_18000642F
0x180006480  mov     cs:PBROADCASTSYSTEMMESSAGEEXW, rdi
0x180006487  lea     rcx, qword_180013630
0x18000648e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180006495  nop     dword ptr [rax+rax+00h]
0x18000649a  xor     eax, eax
0x18000649c  mov     rbx, [rsp+88h+arg_8]
0x1800064a4  add     rsp, 80h
0x1800064ab  pop     rdi
0x1800064ac  retn
0x1800064ae  mov     eax, 0C000000Dh
0x1800064b3  jmp     short loc_18000649C
0x18000d920  push    rbp
0x18000d922  sub     rsp, 40h
0x18000d926  mov     rbp, rdx
0x18000d929  lea     rcx, qword_180013630
0x18000d930  add     rsp, 40h
0x18000d934  pop     rbp
0x18000d935  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
