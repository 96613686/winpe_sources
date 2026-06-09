# winrt::Microsoft::Windows::Workloads::implementation::readResourceContent

- ea: `0x18001e1f0`
- end: `0x18001e301`
- name: `winrt::Microsoft::Windows::Workloads::implementation::readResourceContent`
- size: `273`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x180013330`
- `0x18001e1f0`
- `0x18002b520`
- `0x18003c020`
- `0x18003c6e0`

## import_xrefs

- `KERNEL32!FindResourceW` at `0x18001e224`
- `KERNEL32!FindResourceW` at `0x18001e224`
- `KERNEL32!LockResource` at `0x18001e24a`
- `KERNEL32!LockResource` at `0x18001e24a`
- `KERNEL32!LoadResource` at `0x18001e241`
- `KERNEL32!LoadResource` at `0x18001e241`
- `KERNEL32!SizeofResource` at `0x18001e259`
- `KERNEL32!SizeofResource` at `0x18001e259`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18001e2bf`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18001e2bf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18001e2cb`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18001e2cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::Microsoft::Windows::Workloads::implementation::readResourceContent(
        _QWORD *a1,
        HMODULE a2,
        unsigned __int16 a3)
{
  HRSRC ResourceW; // rax
  HRSRC v6; // rbp
  HGLOBAL Resource; // rax
  const void *v8; // rsi
  DWORD v9; // eax
  size_t v10; // rdi
  void *v11; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  ResourceW = FindResourceW(a2, (LPCWSTR)a3, (LPCWSTR)0x3E8);
  v6 = ResourceW;
  if ( !ResourceW )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xF1,
      (unsigned int)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.Workloads\\WorkloadManager.cpp",
      (const char *)0x80070714LL,
      0);
  Resource = LoadResource(a2, ResourceW);
  v8 = LockResource(Resource);
  v9 = SizeofResource(a2, v6);
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 15;
  *(_BYTE *)a1 = 0;
  v10 = v9;
  std::string::resize(a1, v9, 0);
  v11 = a1;
  if ( a1[3] > 0xFu )
    v11 = (void *)*a1;
  if ( v10 )
  {
    if ( v11 )
    {
      if ( v8 )
      {
        memmove(v11, v8, v10);
        return a1;
      }
      memset(v11, 0, v10);
    }
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
  return a1;
}

```

## disassembly

```asm
0x18001e1f0  mov     [rsp+arg_8], rbx
0x18001e1f5  mov     [rsp+arg_10], rbp
0x18001e1fa  mov     [rsp+arg_18], rsi
0x18001e1ff  mov     [rsp+arg_0], rcx
0x18001e204  push    rdi
0x18001e205  sub     rsp, 30h
0x18001e209  mov     rdi, rdx
0x18001e20c  mov     rbx, rcx
0x18001e20f  mov     [rsp+38h+var_18], 0; int
0x18001e217  movzx   edx, r8w; lpName
0x18001e21b  mov     r8d, 3E8h; lpType
0x18001e221  mov     rcx, rdi; hModule
0x18001e224  call    cs:__imp_FindResourceW
0x18001e22a  mov     rbp, rax
0x18001e22d  mov     rcx, [rsp+38h]; this
0x18001e232  test    rax, rax
0x18001e235  jz      loc_18001E2E9
0x18001e23b  mov     rdx, rax; hResInfo
0x18001e23e  mov     rcx, rdi; hModule
0x18001e241  call    cs:__imp_LoadResource
0x18001e247  mov     rcx, rax; hResData
0x18001e24a  call    cs:__imp_LockResource
0x18001e250  mov     rsi, rax
0x18001e253  mov     rdx, rbp; hResInfo
0x18001e256  mov     rcx, rdi; hModule
0x18001e259  call    cs:__imp_SizeofResource
0x18001e25f  xorps   xmm0, xmm0
0x18001e262  movups  xmmword ptr [rbx], xmm0
0x18001e265  mov     qword ptr [rbx+10h], 0
0x18001e26d  mov     qword ptr [rbx+18h], 0Fh
0x18001e275  mov     byte ptr [rbx], 0
0x18001e278  mov     [rsp+38h+var_18], 1
0x18001e280  mov     edi, eax
0x18001e282  xor     r8d, r8d
0x18001e285  mov     edx, eax
0x18001e287  mov     rcx, rbx
0x18001e28a  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x18001e28f  mov     rcx, rbx
0x18001e292  cmp     qword ptr [rbx+18h], 0Fh
0x18001e297  jbe     short loc_18001E29C
0x18001e299  mov     rcx, [rbx]; void *
0x18001e29c  test    rdi, rdi
0x18001e29f  jz      short loc_18001E2D1
0x18001e2a1  test    rcx, rcx
0x18001e2a4  jz      short loc_18001E2BF
0x18001e2a6  mov     r8, rdi; Size
0x18001e2a9  test    rsi, rsi
0x18001e2ac  jz      short loc_18001E2B8
0x18001e2ae  mov     rdx, rsi; Src
0x18001e2b1  call    memmove
0x18001e2b6  jmp     short loc_18001E2D1
0x18001e2b8  xor     edx, edx; Val
0x18001e2ba  call    memset
0x18001e2bf  call    cs:__imp__errno
0x18001e2c5  mov     dword ptr [rax], 16h
0x18001e2cb  call    cs:__imp__invalid_parameter_noinfo
0x18001e2d1  mov     rax, rbx
0x18001e2d4  mov     rbx, [rsp+38h+arg_8]
0x18001e2d9  mov     rbp, [rsp+38h+arg_10]
0x18001e2de  mov     rsi, [rsp+38h+arg_18]
0x18001e2e3  add     rsp, 30h
0x18001e2e7  pop     rdi
0x18001e2e8  retn
0x18001e2e9  mov     r9d, 80070714h; char *
0x18001e2ef  lea     r8, aCW1SProductApi_0; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18001e2f6  mov     edx, 0F1h; void *
0x18001e2fb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
