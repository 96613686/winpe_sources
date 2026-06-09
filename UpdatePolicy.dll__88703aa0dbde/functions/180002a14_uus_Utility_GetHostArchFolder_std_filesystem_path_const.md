# uus::Utility::GetHostArchFolder(std::filesystem::path const &)

- ea: `0x180002a14`
- end: `0x180002b09`
- name: `?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002db0`

## callees

- `0x180001fe4`
- `0x1800028b4`
- `0x180002a14`
- `0x1800078ac`
- `0x18000ed40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002a4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002a4c`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180002a5f`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180002a5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall uus::Utility::GetHostArchFolder(__int64 a1, struct std::filesystem::path *a2)
{
  HANDLE CurrentProcess; // rax
  _QWORD *ArchFolderFromMachine; // rax
  std::filesystem::path *v6; // rax
  _BYTE Src[32]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v9[32]; // [rsp+50h] [rbp-38h] BYREF
  _WORD v10[2]; // [rsp+70h] [rbp-18h] BYREF
  __int16 v11; // [rsp+74h] [rbp-14h] BYREF

  v11 = 0;
  v10[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)IsWow64Process2(CurrentProcess, &v11, v10) && v10[0] && v10[0] != 0x8664 )
  {
    ArchFolderFromMachine = (_QWORD *)uus::Utility::GetArchFolderFromMachine(v9, v10[0]);
    v6 = std::filesystem::operator/((std::filesystem::path *)Src, a2, ArchFolderFromMachine);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)v6;
    *(_OWORD *)(a1 + 16) = *((_OWORD *)v6 + 1);
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 3) = 7;
    *(_WORD *)v6 = 0;
    *(_BYTE *)(a1 + 32) = 1;
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v9);
  }
  else
  {
    *(_BYTE *)(a1 + 32) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180002a14  mov     [rsp+arg_10], rbx
0x180002a19  mov     [rsp+arg_18], rsi
0x180002a1e  push    rdi
0x180002a1f  sub     rsp, 80h
0x180002a26  mov     rax, cs:__security_cookie
0x180002a2d  xor     rax, rsp
0x180002a30  mov     [rsp+88h+var_10], rax
0x180002a35  mov     rdi, rdx
0x180002a38  mov     rbx, rcx
0x180002a3b  mov     [rsp+88h+var_60], rcx
0x180002a40  xor     esi, esi
0x180002a42  mov     [rsp+88h+var_14], si
0x180002a47  mov     [rsp+88h+var_18], si
0x180002a4c  call    cs:__imp_GetCurrentProcess
0x180002a52  mov     rcx, rax
0x180002a55  lea     r8, [rsp+88h+var_18]
0x180002a5a  lea     rdx, [rsp+88h+var_14]
0x180002a5f  call    cs:__imp_IsWow64Process2
0x180002a65  test    eax, eax
0x180002a67  jz      short loc_180002AE0
0x180002a69  movzx   eax, [rsp+88h+var_18]
0x180002a6e  cmp     si, ax
0x180002a71  jz      short loc_180002AE0
0x180002a73  mov     ecx, 8664h
0x180002a78  cmp     cx, ax
0x180002a7b  jz      short loc_180002AE0
0x180002a7d  mov     edx, eax
0x180002a7f  lea     rcx, [rsp+88h+var_38]
0x180002a84  call    ?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z; uus::Utility::GetArchFolderFromMachine(uint)
0x180002a89  nop
0x180002a8a  mov     r8, rax; void *
0x180002a8d  mov     rdx, rdi; struct std::filesystem::path *
0x180002a90  lea     rcx, [rsp+88h+Src]; Src
0x180002a95  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180002a9a  xorps   xmm0, xmm0
0x180002a9d  movups  xmmword ptr [rbx], xmm0
0x180002aa0  mov     [rbx+10h], rsi
0x180002aa4  mov     [rbx+18h], rsi
0x180002aa8  movups  xmm0, xmmword ptr [rax]
0x180002aab  movups  xmmword ptr [rbx], xmm0
0x180002aae  movups  xmm1, xmmword ptr [rax+10h]
0x180002ab2  movups  xmmword ptr [rbx+10h], xmm1
0x180002ab6  mov     [rax+10h], rsi
0x180002aba  mov     qword ptr [rax+18h], 7
0x180002ac2  mov     [rax], si
0x180002ac5  mov     byte ptr [rbx+20h], 1
0x180002ac9  lea     rcx, [rsp+88h+Src]
0x180002ace  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002ad3  nop
0x180002ad4  lea     rcx, [rsp+88h+var_38]
0x180002ad9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180002ade  jmp     short loc_180002AE4
0x180002ae0  mov     [rbx+20h], sil
0x180002ae4  mov     rax, rbx
0x180002ae7  mov     rcx, [rsp+88h+var_10]
0x180002aec  xor     rcx, rsp; StackCookie
0x180002aef  call    __security_check_cookie
0x180002af4  lea     r11, [rsp+88h+var_8]
0x180002afc  mov     rbx, [r11+20h]
0x180002b00  mov     rsi, [r11+28h]
0x180002b04  mov     rsp, r11
0x180002b07  pop     rdi
0x180002b08  retn
```
