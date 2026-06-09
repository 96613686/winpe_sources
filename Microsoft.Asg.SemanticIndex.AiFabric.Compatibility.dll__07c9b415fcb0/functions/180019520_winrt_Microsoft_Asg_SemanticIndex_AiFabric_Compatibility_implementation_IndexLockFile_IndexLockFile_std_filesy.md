# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(std::filesystem::path,bool)

- ea: `0x180019520`
- end: `0x180019658`
- name: `??0IndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@Vpath@filesystem@std@@_N@Z`
- size: `312`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8)`
- caller_count: `9`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027080`
- `0x180027580`
- `0x18003c3f0`
- `0x18003e920`
- `0x180050d20`
- `0x1800510f0`
- `0x1800567e0`
- `0x180230600`
- `0x18023a270`

## callees

- `0x180007de0`
- `0x180019520`
- `0x180047860`
- `0x1801f7110`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001960d`
- `KERNEL32!SetLastError` at `0x18001960d`
- `KERNEL32!GetLastError` at `0x1800195fa`
- `KERNEL32!GetLastError` at `0x1800195fa`
- `KERNEL32!CloseHandle` at `0x180019605`
- `KERNEL32!CloseHandle` at `0x180019625`
- `KERNEL32!CloseHandle` at `0x180019605`
- `KERNEL32!CloseHandle` at `0x180019625`
- `KERNEL32!CreateFileW` at `0x1800195d9`
- `KERNEL32!CreateFileW` at `0x1800195d9`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3)
{
  int v3; // ebx
  char *v6; // r14
  const WCHAR *v7; // rdi
  char *FileW; // rsi
  void *v9; // rdi
  DWORD LastError; // ebx
  char v12; // [rsp+48h] [rbp-40h] BYREF
  __int64 v13; // [rsp+50h] [rbp-38h]

  v3 = a3;
  v13 = a2;
  *(_BYTE *)a1 = a3;
  *(_OWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_OWORD *)(a1 + 8) = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 24) = *(_OWORD *)(a2 + 16);
  *(_WORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  v6 = (char *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = -1;
  v7 = (const WCHAR *)(a1 + 8);
  std::wstring::append((void *)(a1 + 8));
  if ( *((_QWORD *)v7 + 3) > 7u )
    v7 = *(const WCHAR **)v7;
  FileW = (char *)CreateFileW(v7, 0xC0000000, 0, 0, 2u, (v3 << 26) + 128, 0);
  if ( v6 == &v12 )
  {
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
  }
  else
  {
    v9 = *(void **)v6;
    if ( *(_QWORD *)v6 != -1 && v9 )
    {
      LastError = GetLastError();
      CloseHandle(v9);
      SetLastError(LastError);
    }
    *(_QWORD *)v6 = FileW;
  }
  std::basic_string<char16_t>::_Tidy_deallocate(a2);
  return a1;
}

```

## disassembly

```asm
0x180019520  mov     [rsp+arg_10], rbx
0x180019525  push    rbp
0x180019526  push    rsi
0x180019527  push    rdi
0x180019528  push    r14
0x18001952a  push    r15
0x18001952c  sub     rsp, 60h
0x180019530  mov     rax, cs:__security_cookie
0x180019537  xor     rax, rsp
0x18001953a  mov     [rsp+88h+var_30], rax
0x18001953f  movzx   ebx, r8b
0x180019543  mov     rbp, rdx
0x180019546  mov     r15, rcx
0x180019549  mov     [rsp+88h+var_48], rcx
0x18001954e  mov     [rsp+88h+var_38], rdx
0x180019553  mov     [rcx], bl
0x180019555  xorps   xmm0, xmm0
0x180019558  movups  xmmword ptr [rcx+8], xmm0
0x18001955c  xor     esi, esi
0x18001955e  mov     [rcx+18h], rsi
0x180019562  mov     [rcx+20h], rsi
0x180019566  movups  xmm0, xmmword ptr [rdx]
0x180019569  movups  xmmword ptr [rcx+8], xmm0
0x18001956d  movups  xmm1, xmmword ptr [rdx+10h]
0x180019571  movups  xmmword ptr [rcx+18h], xmm1
0x180019575  mov     [rdx], si
0x180019578  mov     [rdx+10h], rsi
0x18001957c  mov     qword ptr [rdx+18h], 7
0x180019584  lea     r14, [rcx+28h]
0x180019588  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18001958f  lea     rdi, [rcx+8]
0x180019593  mov     r8d, 5
0x180019599  lea     rdx, aLock; ".lock"
0x1800195a0  mov     rcx, rdi; Src
0x1800195a3  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1800195a8  mov     eax, ebx
0x1800195aa  shl     eax, 1Ah
0x1800195ad  sub     eax, 0FFFFFF80h
0x1800195b0  cmp     qword ptr [rdi+18h], 7
0x1800195b5  jbe     short loc_1800195BA
0x1800195b7  mov     rdi, [rdi]
0x1800195ba  mov     [rsp+88h+hTemplateFile], rsi; hTemplateFile
0x1800195bf  mov     [rsp+88h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1800195c3  mov     [rsp+88h+dwCreationDisposition], 2; dwCreationDisposition
0x1800195cb  xor     r9d, r9d; lpSecurityAttributes
0x1800195ce  xor     r8d, r8d; dwShareMode
0x1800195d1  mov     edx, 0C0000000h; dwDesiredAccess
0x1800195d6  mov     rcx, rdi; lpFileName
0x1800195d9  call    cs:__imp_CreateFileW
0x1800195df  mov     rsi, rax
0x1800195e2  lea     rax, [rsp+88h+var_40]
0x1800195e7  cmp     r14, rax
0x1800195ea  jz      short loc_180019618
0x1800195ec  mov     rdi, [r14]
0x1800195ef  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800195f3  jz      short loc_180019613
0x1800195f5  test    rdi, rdi
0x1800195f8  jz      short loc_180019613
0x1800195fa  call    cs:__imp_GetLastError
0x180019600  mov     ebx, eax
0x180019602  mov     rcx, rdi; hObject
0x180019605  call    cs:__imp_CloseHandle
0x18001960b  mov     ecx, ebx; dwErrCode
0x18001960d  call    cs:__imp_SetLastError
0x180019613  mov     [r14], rsi
0x180019616  jmp     short loc_18001962C
0x180019618  lea     rdx, [rsi-1]
0x18001961c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180019620  ja      short loc_18001962C
0x180019622  mov     rcx, rsi; hObject
0x180019625  call    cs:__imp_CloseHandle
0x18001962b  nop
0x18001962c  mov     rcx, rbp
0x18001962f  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x180019634  mov     rax, r15
0x180019637  mov     rcx, [rsp+88h+var_30]
0x18001963c  xor     rcx, rsp; StackCookie
0x18001963f  call    __security_check_cookie
0x180019644  mov     rbx, [rsp+88h+arg_10]
0x18001964c  add     rsp, 60h
0x180019650  pop     r15
0x180019652  pop     r14
0x180019654  pop     rdi
0x180019655  pop     rsi
0x180019656  pop     rbp
0x180019657  retn
```
