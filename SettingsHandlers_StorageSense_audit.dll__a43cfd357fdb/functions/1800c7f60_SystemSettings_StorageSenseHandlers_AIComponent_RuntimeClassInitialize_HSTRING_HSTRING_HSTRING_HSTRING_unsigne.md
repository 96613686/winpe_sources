# SystemSettings::StorageSenseHandlers::AIComponent::RuntimeClassInitialize(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ *,unsigned __int64)

- ea: `0x1800c7f60`
- end: `0x1800c806e`
- name: `?RuntimeClassInitialize@AIComponent@StorageSenseHandlers@SystemSettings@@QEAAJPEAUHSTRING__@@000_K@Z`
- size: `270`
- prototype: `int(SystemSettings::StorageSenseHandlers::AIComponent *__hidden this, HSTRING, HSTRING, HSTRING, HSTRING, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180093fa8`

## callees

- `0x18000e6cc`
- `0x1800c7f60`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c7f94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c7fdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c800d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c803f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c7f94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c7fdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c800d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c803f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7f81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7fca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7ffa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c802a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7f81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7fca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7ffa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c802a`

## string_xrefs

- `0x1800c7faa`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\aicomponent.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::AIComponent::RuntimeClassInitialize(
        HSTRING *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4,
        HSTRING string,
        HSTRING a6)
{
  HSTRING *v6; // rbx
  HRESULT v11; // ebx
  __int64 v12; // rdx
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v6 = this + 30;
  WindowsDeleteString(this[30]);
  *v6 = 0;
  v11 = WindowsDuplicateString(a2, v6);
  if ( v11 < 0 )
  {
    v12 = 29;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\aicomponent.cpp",
      (const char *)(unsigned int)v11,
      v14);
    return (unsigned int)v11;
  }
  WindowsDeleteString(this[31]);
  this[31] = 0;
  v11 = WindowsDuplicateString(a3, this + 31);
  if ( v11 < 0 )
  {
    v12 = 30;
    goto LABEL_3;
  }
  WindowsDeleteString(this[32]);
  this[32] = 0;
  v11 = WindowsDuplicateString(a4, this + 32);
  if ( v11 < 0 )
  {
    v12 = 31;
    goto LABEL_3;
  }
  WindowsDeleteString(this[33]);
  this[33] = 0;
  v11 = WindowsDuplicateString(string, this + 33);
  if ( v11 < 0 )
  {
    v12 = 32;
    goto LABEL_3;
  }
  this[34] = a6;
  return 0;
}

```

## disassembly

```asm
0x1800c7f60  push    rbx
0x1800c7f62  push    rbp
0x1800c7f63  push    rsi
0x1800c7f64  push    rdi
0x1800c7f65  push    r14; int
0x1800c7f67  sub     rsp, 20h
0x1800c7f6b  lea     rbx, [rcx+0F0h]
0x1800c7f72  mov     rsi, rcx
0x1800c7f75  mov     rcx, [rbx]; string
0x1800c7f78  mov     r14, r9
0x1800c7f7b  mov     rbp, r8
0x1800c7f7e  mov     rdi, rdx
0x1800c7f81  call    cs:__imp_WindowsDeleteString
0x1800c7f87  mov     rdx, rbx; newString
0x1800c7f8a  mov     qword ptr [rbx], 0
0x1800c7f91  mov     rcx, rdi; string
0x1800c7f94  call    cs:__imp_WindowsDuplicateString
0x1800c7f9a  mov     ebx, eax
0x1800c7f9c  test    eax, eax
0x1800c7f9e  jns     short loc_1800C7FC0
0x1800c7fa0  mov     edx, 1Dh; void *
0x1800c7fa5  mov     rcx, [rsp+48h]; this
0x1800c7faa  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\coresettinghandlers"...
0x1800c7fb1  mov     r9d, ebx; char *
0x1800c7fb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7fb9  mov     eax, ebx
0x1800c7fbb  jmp     loc_1800C8063
0x1800c7fc0  lea     rbx, [rsi+0F8h]
0x1800c7fc7  mov     rcx, [rbx]; string
0x1800c7fca  call    cs:__imp_WindowsDeleteString
0x1800c7fd0  mov     rdx, rbx; newString
0x1800c7fd3  mov     qword ptr [rbx], 0
0x1800c7fda  mov     rcx, rbp; string
0x1800c7fdd  call    cs:__imp_WindowsDuplicateString
0x1800c7fe3  mov     ebx, eax
0x1800c7fe5  test    eax, eax
0x1800c7fe7  jns     short loc_1800C7FF0
0x1800c7fe9  mov     edx, 1Eh
0x1800c7fee  jmp     short loc_1800C7FA5
0x1800c7ff0  lea     rbx, [rsi+100h]
0x1800c7ff7  mov     rcx, [rbx]; string
0x1800c7ffa  call    cs:__imp_WindowsDeleteString
0x1800c8000  mov     rdx, rbx; newString
0x1800c8003  mov     qword ptr [rbx], 0
0x1800c800a  mov     rcx, r14; string
0x1800c800d  call    cs:__imp_WindowsDuplicateString
0x1800c8013  mov     ebx, eax
0x1800c8015  test    eax, eax
0x1800c8017  jns     short loc_1800C8020
0x1800c8019  mov     edx, 1Fh
0x1800c801e  jmp     short loc_1800C7FA5
0x1800c8020  lea     rbx, [rsi+108h]
0x1800c8027  mov     rcx, [rbx]; string
0x1800c802a  call    cs:__imp_WindowsDeleteString
0x1800c8030  mov     rcx, [rsp+48h+string]; string
0x1800c8035  mov     rdx, rbx; newString
0x1800c8038  mov     qword ptr [rbx], 0
0x1800c803f  call    cs:__imp_WindowsDuplicateString
0x1800c8045  mov     ebx, eax
0x1800c8047  test    eax, eax
0x1800c8049  jns     short loc_1800C8055
0x1800c804b  mov     edx, 20h ; ' '
0x1800c8050  jmp     loc_1800C7FA5
0x1800c8055  mov     rax, [rsp+48h+arg_28]
0x1800c805a  mov     [rsi+110h], rax
0x1800c8061  xor     eax, eax
0x1800c8063  add     rsp, 20h
0x1800c8067  pop     r14
0x1800c8069  pop     rdi
0x1800c806a  pop     rsi
0x1800c806b  pop     rbp
0x1800c806c  pop     rbx
0x1800c806d  retn
```
