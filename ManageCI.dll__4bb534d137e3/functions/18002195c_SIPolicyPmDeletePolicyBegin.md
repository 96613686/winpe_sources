# SIPolicyPmDeletePolicyBegin

- ea: `0x18002195c`
- end: `0x180021a30`
- name: `SIPolicyPmDeletePolicyBegin`
- size: `212`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int8, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180011c00`

## callees

- `0x180020b44`
- `0x180021930`
- `0x18002195c`
- `0x18002234c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800219f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800219f2`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180021977`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180021977`
- `ntdll!RtlFreeUnicodeString` at `0x180021a17`
- `ntdll!RtlFreeUnicodeString` at `0x180021a17`

## pseudocode

```c
__int64 __fastcall SIPolicyPmDeletePolicyBegin(_QWORD *a1, unsigned __int8 a2, _QWORD *a3)
{
  char IsStateSeparationEnabled; // al
  struct _UNICODE_STRING *p_UnicodeString; // r10
  __int64 v8; // rcx
  int v9; // ebx
  _BYTE *v10; // rax
  __int128 v11; // xmm0
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-58h] BYREF
  struct _UNICODE_STRING v14; // [rsp+40h] [rbp-48h] BYREF
  __int64 v15; // [rsp+50h] [rbp-38h]

  UnicodeString = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  p_UnicodeString = &UnicodeString;
  if ( a2 )
    p_UnicodeString = 0;
  v9 = SIPolicyPmBuildPathFromPolicyID(
         a1,
         0,
         IsStateSeparationEnabled,
         (struct _UNICODE_STRING *)((unsigned __int64)&UnicodeString & -(__int64)(a2 != 0)),
         p_UnicodeString,
         0);
  if ( v9 >= 0 )
  {
    v14 = UnicodeString;
    v15 = a2;
    if ( SIPolicyPmDoesPolicyExist(v8, &v14) )
    {
      v10 = LocalAlloc(0x40u, 0x28u);
      if ( v10 )
      {
        v11 = *(_OWORD *)a1;
        v10[32] = a2;
        *(_OWORD *)v10 = v11;
        *a3 = v10;
      }
      else
      {
        v9 = -1073741801;
      }
    }
    else
    {
      v9 = -1073741275;
    }
  }
  RtlFreeUnicodeString(&UnicodeString);
  SIPolicyPmCloseTransactionHandle(0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002195c  push    rbx
0x18002195e  push    rsi
0x18002195f  push    rdi
0x180021960  push    r14
0x180021962  sub     rsp, 68h
0x180021966  xorps   xmm0, xmm0
0x180021969  mov     r14, r8
0x18002196c  movups  xmmword ptr [rsp+88h+UnicodeString.Length], xmm0
0x180021971  mov     dil, dl
0x180021974  mov     rsi, rcx
0x180021977  call    cs:__imp_RtlIsStateSeparationEnabled
0x18002197d  xor     r9d, r9d
0x180021980  mov     [rsp+88h+var_60], 0
0x180021989  test    dil, dil
0x18002198c  lea     rcx, [rsp+88h+UnicodeString]
0x180021991  lea     r10, [rsp+88h+UnicodeString]
0x180021996  mov     r8b, al
0x180021999  cmovnz  r10, r9
0x18002199d  mov     r9b, dil
0x1800219a0  neg     r9b
0x1800219a3  mov     [rsp+88h+var_68], r10
0x1800219a8  sbb     r9, r9
0x1800219ab  xor     edx, edx
0x1800219ad  and     r9, rcx
0x1800219b0  mov     rcx, rsi
0x1800219b3  call    SIPolicyPmBuildPathFromPolicyID
0x1800219b8  mov     ebx, eax
0x1800219ba  test    eax, eax
0x1800219bc  js      short loc_180021A12
0x1800219be  movups  xmm0, xmmword ptr [rsp+88h+UnicodeString.Length]
0x1800219c3  xor     eax, eax
0x1800219c5  lea     rdx, [rsp+88h+var_48]
0x1800219ca  mov     [rsp+88h+var_38], rax
0x1800219cf  movdqu  [rsp+88h+var_48], xmm0
0x1800219d5  mov     byte ptr [rsp+88h+var_38], dil
0x1800219da  call    SIPolicyPmDoesPolicyExist
0x1800219df  test    al, al
0x1800219e1  jnz     short loc_1800219EA
0x1800219e3  mov     ebx, 0C0000225h
0x1800219e8  jmp     short loc_180021A12
0x1800219ea  mov     edx, 28h ; '('; uBytes
0x1800219ef  lea     ecx, [rdx+18h]; uFlags
0x1800219f2  call    cs:__imp_LocalAlloc
0x1800219f8  test    rax, rax
0x1800219fb  jnz     short loc_180021A04
0x1800219fd  mov     ebx, 0C0000017h
0x180021a02  jmp     short loc_180021A12
0x180021a04  movups  xmm0, xmmword ptr [rsi]
0x180021a07  mov     [rax+20h], dil
0x180021a0b  movdqu  xmmword ptr [rax], xmm0
0x180021a0f  mov     [r14], rax
0x180021a12  lea     rcx, [rsp+88h+UnicodeString]; UnicodeString
0x180021a17  call    cs:__imp_RtlFreeUnicodeString
0x180021a1d  xor     ecx, ecx; hMem
0x180021a1f  call    SIPolicyPmCloseTransactionHandle
0x180021a24  mov     eax, ebx
0x180021a26  add     rsp, 68h
0x180021a2a  pop     r14
0x180021a2c  pop     rdi
0x180021a2d  pop     rsi
0x180021a2e  pop     rbx
0x180021a2f  retn
```
