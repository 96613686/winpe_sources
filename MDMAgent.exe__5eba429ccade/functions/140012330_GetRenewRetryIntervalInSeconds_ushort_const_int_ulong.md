# GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)

- ea: `0x140012330`
- end: `0x140012452`
- name: `?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z`
- size: `290`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140007f34`

## callees

- `0x140007724`
- `0x14000b288`
- `0x140012330`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012439`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012439`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012396`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012396`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400123cf`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400123cf`

## pseudocode

```c
__int64 __fastcall GetRenewRetryIntervalInSeconds(const unsigned __int16 *a1, int a2, unsigned int *a3)
{
  int v6; // edi
  const WCHAR *v7; // rax
  LSTATUS v8; // eax
  signed int v9; // ebx
  HKEY v10; // rcx
  const unsigned __int16 *v11; // r8
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+78h] [rbp+38h] BYREF
  unsigned int v15; // [rsp+88h] [rbp+48h] BYREF

  v15 = 0;
  hKey = 0;
  v6 = a2 != 0 ? 604800 : 1209600;
  v14 = v6;
  v7 = (const WCHAR *)DMGetKnownRegPath(1);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  v10 = hKey;
  if ( v9 >= 0 )
  {
    v11 = L"RetryInterval";
    if ( !a2 )
      v11 = L"RetryAfterExpiryInterval";
    if ( (int)OmaDmRegistryGetDWORD(hKey, a1, v11, &v15) >= 0 )
    {
      v9 = ULongLongToULong(24LL * v15, &v14);
      if ( v9 < 0 )
        goto LABEL_13;
      v9 = ULongLongToULong(60LL * v14, &v14);
      if ( v9 < 0 )
        goto LABEL_13;
      v9 = ULongLongToULong(60LL * v14, &v14);
      if ( v9 < 0 )
        goto LABEL_13;
      v6 = v14;
    }
    else
    {
      v9 = 0;
    }
    *a3 = v6;
LABEL_13:
    v10 = hKey;
  }
  hKey = 0;
  if ( v10 )
    RegCloseKey(v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140012330  mov     [rsp-28h+arg_0], rbx
0x140012335  push    rbp
0x140012336  push    rsi
0x140012337  push    rdi
0x140012338  push    r14
0x14001233a  push    r15
0x14001233c  mov     rbp, rsp
0x14001233f  sub     rsp, 40h
0x140012343  mov     eax, edx
0x140012345  mov     [rbp+arg_18], 0
0x14001234c  neg     eax
0x14001234e  mov     [rbp+hKey], 0
0x140012356  mov     r15, rcx
0x140012359  mov     rsi, r8
0x14001235c  sbb     edi, edi
0x14001235e  mov     ecx, 1
0x140012363  and     edi, 0FFF6C580h
0x140012369  mov     r14d, edx
0x14001236c  add     edi, 127500h
0x140012372  mov     [rbp+arg_8], edi
0x140012375  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x14001237a  lea     rcx, [rbp+hKey]
0x14001237e  mov     r9d, 20019h; samDesired
0x140012384  mov     [rsp+40h+phkResult], rcx; phkResult
0x140012389  xor     r8d, r8d; ulOptions
0x14001238c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012393  mov     rdx, rax; lpSubKey
0x140012396  call    cs:__imp_RegOpenKeyExW
0x14001239c  mov     ebx, eax
0x14001239e  test    eax, eax
0x1400123a0  jle     short loc_1400123AB
0x1400123a2  movzx   ebx, ax
0x1400123a5  or      ebx, 80070000h
0x1400123ab  mov     rcx, [rbp+hKey]
0x1400123af  test    ebx, ebx
0x1400123b1  js      short loc_14001242C
0x1400123b3  lea     rax, aRetryafterexpi; "RetryAfterExpiryInterval"
0x1400123ba  test    r14d, r14d
0x1400123bd  lea     r8, aRetryinterval; "RetryInterval"
0x1400123c4  mov     rdx, r15
0x1400123c7  cmovz   r8, rax
0x1400123cb  lea     r9, [rbp+arg_18]
0x1400123cf  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400123d5  test    eax, eax
0x1400123d7  jns     short loc_1400123DD
0x1400123d9  xor     ebx, ebx
0x1400123db  jmp     short loc_140012426
0x1400123dd  mov     eax, [rbp+arg_18]
0x1400123e0  lea     rdx, [rbp+arg_8]; unsigned int *
0x1400123e4  lea     rcx, [rax+rax*2]
0x1400123e8  shl     rcx, 3; unsigned __int64
0x1400123ec  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1400123f1  mov     ebx, eax
0x1400123f3  test    eax, eax
0x1400123f5  js      short loc_140012428
0x1400123f7  mov     eax, [rbp+arg_8]
0x1400123fa  lea     rdx, [rbp+arg_8]; unsigned int *
0x1400123fe  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x140012402  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140012407  mov     ebx, eax
0x140012409  test    eax, eax
0x14001240b  js      short loc_140012428
0x14001240d  mov     eax, [rbp+arg_8]
0x140012410  lea     rdx, [rbp+arg_8]; unsigned int *
0x140012414  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x140012418  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14001241d  mov     ebx, eax
0x14001241f  test    eax, eax
0x140012421  js      short loc_140012428
0x140012423  mov     edi, [rbp+arg_8]
0x140012426  mov     [rsi], edi
0x140012428  mov     rcx, [rbp+hKey]; hKey
0x14001242c  mov     [rbp+hKey], 0
0x140012434  test    rcx, rcx
0x140012437  jz      short loc_14001243F
0x140012439  call    cs:__imp_RegCloseKey
0x14001243f  mov     eax, ebx
0x140012441  mov     rbx, [rsp+40h+arg_0]
0x140012446  add     rsp, 40h
0x14001244a  pop     r15
0x14001244c  pop     r14
0x14001244e  pop     rdi
0x14001244f  pop     rsi
0x140012450  pop     rbp
0x140012451  retn
```
