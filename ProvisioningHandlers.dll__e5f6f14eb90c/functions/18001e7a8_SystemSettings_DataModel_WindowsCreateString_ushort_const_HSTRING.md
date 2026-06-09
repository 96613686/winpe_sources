# SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)

- ea: `0x18001e7a8`
- end: `0x18001e835`
- name: `?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(SystemSettings::DataModel *__hidden this, const unsigned __int16 *, HSTRING *)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018880`
- `0x180020d70`
- `0x1800210f0`
- `0x180021250`
- `0x180021590`
- `0x180021630`
- `0x1800216d0`
- `0x180021770`
- `0x180021810`

## callees

- `0x18001cbe4`
- `0x18001e560`
- `0x18001e7a8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e816`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e816`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::WindowsCreateString(const WCHAR *this, unsigned __int16 *a2, HSTRING *a3)
{
  const WCHAR *v3; // r9
  unsigned __int64 v5; // rcx
  int v6; // ebx
  const unsigned __int16 *v7; // r9
  HSTRING v8; // r10
  HRESULT v9; // eax
  unsigned int v11; // [rsp+30h] [rbp+8h] BYREF
  HSTRING v12; // [rsp+38h] [rbp+10h] BYREF

  v3 = &word_1800330E8;
  v12 = 0;
  v11 = 0;
  if ( this )
    v3 = this;
  v5 = -1;
  do
    ++v5;
  while ( v3[v5] );
  v6 = ULongLongToUInt(v5, &v11);
  if ( v6 >= 0 )
  {
    v9 = Microsoft::WRL::Wrappers::HString::Set(&v12, v7, v11);
    v8 = v12;
    v6 = v9;
  }
  v12 = 0;
  *(_QWORD *)a2 = v8;
  WindowsDeleteString(0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001e7a8  mov     rax, rsp
0x18001e7ab  mov     [rax+18h], rbx
0x18001e7af  mov     [rax+20h], rsi
0x18001e7b3  push    rdi
0x18001e7b4  sub     rsp, 20h
0x18001e7b8  xor     esi, esi
0x18001e7ba  lea     r9, word_1800330E8
0x18001e7c1  test    rcx, rcx
0x18001e7c4  mov     [rax+10h], rsi
0x18001e7c8  mov     rdi, rdx
0x18001e7cb  mov     [rax+8], esi
0x18001e7ce  cmovnz  r9, rcx
0x18001e7d2  mov     r10d, esi
0x18001e7d5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001e7d9  inc     rcx; unsigned __int64
0x18001e7dc  cmp     [r9+rcx*2], si
0x18001e7e1  jnz     short loc_18001E7D9
0x18001e7e3  lea     rdx, [rsp+28h+arg_0]; unsigned int *
0x18001e7e8  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18001e7ed  mov     ebx, eax
0x18001e7ef  test    eax, eax
0x18001e7f1  js      short loc_18001E80C
0x18001e7f3  mov     r8d, [rsp+28h+arg_0]; unsigned int
0x18001e7f8  lea     rcx, [rsp+28h+arg_8]; this
0x18001e7fd  mov     rdx, r9; unsigned __int16 *
0x18001e800  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18001e805  mov     r10, [rsp+28h+arg_8]
0x18001e80a  mov     ebx, eax
0x18001e80c  xor     ecx, ecx; string
0x18001e80e  mov     [rsp+28h+arg_8], rsi
0x18001e813  mov     [rdi], r10
0x18001e816  call    cs:__imp_WindowsDeleteString
0x18001e81d  nop     dword ptr [rax+rax+00h]
0x18001e822  mov     rsi, [rsp+28h+arg_18]
0x18001e827  mov     eax, ebx
0x18001e829  mov     rbx, [rsp+28h+arg_10]
0x18001e82e  add     rsp, 20h
0x18001e832  pop     rdi
0x18001e833  retn
```
