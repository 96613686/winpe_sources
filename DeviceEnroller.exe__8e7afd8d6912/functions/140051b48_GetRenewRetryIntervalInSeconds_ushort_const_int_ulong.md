# GetRenewRetryIntervalInSeconds(ushort const *,int,ulong *)

- ea: `0x140051b48`
- end: `0x140051c61`
- name: `?GetRenewRetryIntervalInSeconds@@YAJPEBGHPEAK@Z`
- size: `281`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x14002c1b0`

## callees

- `0x140051b48`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140051bf2`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140051bf2`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140051b85`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140051b85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140051bb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140051bb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051c46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140051c46`

## pseudocode

```c
__int64 __fastcall GetRenewRetryIntervalInSeconds(const unsigned __int16 *a1, int a2, unsigned int *a3)
{
  unsigned __int64 v6; // rdi
  char IsStateSeparationEnabled; // al
  LSTATUS v8; // eax
  signed int v9; // ebx
  HKEY v10; // rcx
  const unsigned __int16 *v11; // r8
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  unsigned int v15; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  v15 = 0;
  hKey = 0;
  LODWORD(v6) = a2 != 0 ? 604800 : 1209600;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)off_14005EF50 + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x20019u,
         &hKey);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  v10 = hKey;
  if ( v9 >= 0 )
  {
    v11 = L"RetryInterval";
    if ( !a2 )
      v11 = L"RetryAfterExpiryInterval";
    if ( (int)OmaDmRegistryGetDWORD(hKey, a1, v11, &v15) >= 0
      && ((v12 = 24LL * v15, v12 > 0xFFFFFFFF)
       || (v13 = 60LL * (unsigned int)v12, v13 > 0xFFFFFFFF)
       || (v6 = 60LL * (unsigned int)v13, v6 > 0xFFFFFFFF)) )
    {
      v9 = -2147024362;
    }
    else
    {
      v9 = 0;
      *a3 = v6;
    }
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
0x140051b48  mov     [rsp+arg_0], rbx
0x140051b4d  mov     [rsp+arg_10], rbp
0x140051b52  push    rsi
0x140051b53  push    rdi
0x140051b54  push    r14
0x140051b56  sub     rsp, 30h
0x140051b5a  mov     eax, edx
0x140051b5c  mov     [rsp+48h+arg_8], 0
0x140051b64  neg     eax
0x140051b66  mov     [rsp+48h+hKey], 0
0x140051b6f  mov     rsi, r8
0x140051b72  mov     ebp, edx
0x140051b74  sbb     edi, edi
0x140051b76  mov     r14, rcx
0x140051b79  and     edi, 0FFF6C580h
0x140051b7f  add     edi, 127500h
0x140051b85  call    cs:__imp_RtlIsStateSeparationEnabled
0x140051b8b  lea     rcx, off_14005EF50; "Software\\Microsoft\\Enrollments"
0x140051b92  mov     r9d, 20019h; samDesired
0x140051b98  neg     al
0x140051b9a  lea     rax, [rsp+48h+hKey]
0x140051b9f  sbb     rdx, rdx
0x140051ba2  mov     [rsp+48h+phkResult], rax; phkResult
0x140051ba7  and     edx, 8
0x140051baa  xor     r8d, r8d; ulOptions
0x140051bad  mov     rdx, [rdx+rcx]; lpSubKey
0x140051bb1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140051bb8  call    cs:__imp_RegOpenKeyExW
0x140051bbe  mov     ebx, eax
0x140051bc0  test    eax, eax
0x140051bc2  jle     short loc_140051BCD
0x140051bc4  movzx   ebx, ax
0x140051bc7  or      ebx, 80070000h
0x140051bcd  mov     rcx, [rsp+48h+hKey]
0x140051bd2  test    ebx, ebx
0x140051bd4  js      short loc_140051C38
0x140051bd6  lea     rax, aRetryafterexpi; "RetryAfterExpiryInterval"
0x140051bdd  test    ebp, ebp
0x140051bdf  lea     r8, aRetryinterval; "RetryInterval"
0x140051be6  mov     rdx, r14
0x140051be9  cmovz   r8, rax
0x140051bed  lea     r9, [rsp+48h+arg_8]
0x140051bf2  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140051bf8  test    eax, eax
0x140051bfa  js      short loc_140051C28
0x140051bfc  mov     eax, [rsp+48h+arg_8]
0x140051c00  mov     edx, 0FFFFFFFFh
0x140051c05  lea     rcx, [rax+rax*2]
0x140051c09  shl     rcx, 3
0x140051c0d  cmp     rcx, rdx
0x140051c10  ja      short loc_140051C2E
0x140051c12  mov     eax, ecx
0x140051c14  imul    rcx, rax, 3Ch ; '<'
0x140051c18  cmp     rcx, rdx
0x140051c1b  ja      short loc_140051C2E
0x140051c1d  mov     eax, ecx
0x140051c1f  imul    rdi, rax, 3Ch ; '<'
0x140051c23  cmp     rdi, rdx
0x140051c26  ja      short loc_140051C2E
0x140051c28  xor     ebx, ebx
0x140051c2a  mov     [rsi], edi
0x140051c2c  jmp     short loc_140051C33
0x140051c2e  mov     ebx, 80070216h
0x140051c33  mov     rcx, [rsp+48h+hKey]; hKey
0x140051c38  mov     [rsp+48h+hKey], 0
0x140051c41  test    rcx, rcx
0x140051c44  jz      short loc_140051C4C
0x140051c46  call    cs:__imp_RegCloseKey
0x140051c4c  mov     rbp, [rsp+48h+arg_10]
0x140051c51  mov     eax, ebx
0x140051c53  mov     rbx, [rsp+48h+arg_0]
0x140051c58  add     rsp, 30h
0x140051c5c  pop     r14
0x140051c5e  pop     rdi
0x140051c5f  pop     rsi
0x140051c60  retn
```
