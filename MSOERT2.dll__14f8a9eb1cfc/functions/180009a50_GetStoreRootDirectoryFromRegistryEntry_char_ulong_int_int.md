# GetStoreRootDirectoryFromRegistryEntry(char *,ulong,int,int *)

- ea: `0x180009a50`
- end: `0x180009b0f`
- name: `?GetStoreRootDirectoryFromRegistryEntry@@YAJPEADKHPEAH@Z`
- size: `191`
- prototype: `__int64 __fastcall(char *, unsigned int, int, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180009a50`
- `0x180009b20`
- `0x1800119b4`
- `0x180011a78`
- `0x180012f8e`
- `0x180012fc0`

## pseudocode

```c
int __fastcall GetStoreRootDirectoryFromRegistryEntry(char *a1, int a2, int a3, int *a4)
{
  unsigned int v8; // ecx
  int result; // eax
  unsigned int v10[4]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-238h] BYREF

  memset_0(pszPath, 0, 0x208u);
  v10[0] = 0;
  result = HrSHAnsiToUnicodeCP(v8, a1, pszPath, 260, v10);
  if ( result >= 0 )
  {
    result = GetStoreRootDirectoryFromRegistryEntryW(pszPath, 0x104u, a3, a4);
    if ( result >= 0 )
      return HrSHUnicodeToAnsiCP(0, pszPath, a1, a2, v10);
  }
  return result;
}

```

## disassembly

```asm
0x180009a50  mov     [rsp+arg_10], rbx
0x180009a55  push    rbp
0x180009a56  push    rsi
0x180009a57  push    rdi
0x180009a58  sub     rsp, 260h
0x180009a5f  mov     rax, cs:__security_cookie
0x180009a66  xor     rax, rsp
0x180009a69  mov     [rsp+278h+var_28], rax
0x180009a71  mov     esi, r8d
0x180009a74  mov     edi, edx
0x180009a76  mov     rbx, rcx
0x180009a79  xor     edx, edx; Val
0x180009a7b  mov     r8d, 208h; Size
0x180009a81  lea     rcx, [rsp+278h+pszPath]; void *
0x180009a86  mov     rbp, r9
0x180009a89  call    memset_0
0x180009a8e  lea     rax, [rsp+278h+var_248]
0x180009a93  mov     [rsp+278h+var_248], 0
0x180009a9b  mov     r9d, 104h; int
0x180009aa1  mov     [rsp+278h+var_258], rax; unsigned int *
0x180009aa6  lea     r8, [rsp+278h+pszPath]; unsigned __int16 *
0x180009aab  mov     rdx, rbx; char *
0x180009aae  call    ?HrSHAnsiToUnicodeCP@@YAJIPEBDPEAGHPEAK@Z; HrSHAnsiToUnicodeCP(uint,char const *,ushort *,int,ulong *)
0x180009ab3  test    eax, eax
0x180009ab5  js      short loc_180009AEC
0x180009ab7  mov     r9, rbp; int *
0x180009aba  lea     rcx, [rsp+278h+pszPath]; pszPath
0x180009abf  mov     r8d, esi; int
0x180009ac2  mov     edx, 104h; unsigned int
0x180009ac7  call    ?GetStoreRootDirectoryFromRegistryEntryW@@YAJPEAGKHPEAH@Z; GetStoreRootDirectoryFromRegistryEntryW(ushort *,ulong,int,int *)
0x180009acc  test    eax, eax
0x180009ace  js      short loc_180009AEC
0x180009ad0  lea     rax, [rsp+278h+var_248]
0x180009ad5  mov     r9d, edi; int
0x180009ad8  mov     r8, rbx; char *
0x180009adb  mov     [rsp+278h+var_258], rax; unsigned int *
0x180009ae0  lea     rdx, [rsp+278h+pszPath]; unsigned __int16 *
0x180009ae5  xor     ecx, ecx; unsigned int
0x180009ae7  call    ?HrSHUnicodeToAnsiCP@@YAJIPEBGPEADHPEAK@Z; HrSHUnicodeToAnsiCP(uint,ushort const *,char *,int,ulong *)
0x180009aec  mov     rcx, [rsp+278h+var_28]
0x180009af4  xor     rcx, rsp; StackCookie
0x180009af7  call    __security_check_cookie
0x180009afc  mov     rbx, [rsp+278h+arg_10]
0x180009b04  add     rsp, 260h
0x180009b0b  pop     rdi
0x180009b0c  pop     rsi
0x180009b0d  pop     rbp
0x180009b0e  retn
```
