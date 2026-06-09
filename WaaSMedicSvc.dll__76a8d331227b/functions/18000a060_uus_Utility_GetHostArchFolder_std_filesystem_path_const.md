# uus::Utility::GetHostArchFolder(std::filesystem::path const &)

- ea: `0x18000a060`
- end: `0x18000a160`
- name: `?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009b34`

## callees

- `0x180002200`
- `0x180008f20`
- `0x180009208`
- `0x180009e98`
- `0x18000a060`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a093`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a093`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18000a0a6`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18000a0a6`

## pseudocode

```c
__int64 __fastcall uus::Utility::GetHostArchFolder(__int64 a1, struct std::filesystem::path *a2)
{
  HANDLE CurrentProcess; // rax
  std::filesystem *ArchFolderFromMachine; // rax
  __int64 v6; // rax
  _WORD v8[2]; // [rsp+20h] [rbp-68h] BYREF
  _WORD v9[6]; // [rsp+24h] [rbp-64h] BYREF
  __int64 v10; // [rsp+30h] [rbp-58h]
  _BYTE Src[32]; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v12[32]; // [rsp+58h] [rbp-30h] BYREF

  v10 = a1;
  v9[0] = 0;
  v8[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)IsWow64Process2(CurrentProcess, v9, v8) && v8[0] && v8[0] != 0x8664 )
  {
    ArchFolderFromMachine = (std::filesystem *)uus::Utility::GetArchFolderFromMachine(v12, v8[0]);
    v6 = std::filesystem::operator/(Src, a2, ArchFolderFromMachine);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)v6;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(v6 + 16);
    *(_QWORD *)(v6 + 16) = 0;
    *(_QWORD *)(v6 + 24) = 7;
    *(_WORD *)v6 = 0;
    *(_BYTE *)(a1 + 32) = 1;
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v12);
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
0x18000a060  mov     [rsp+arg_10], rbx
0x18000a065  push    rdi
0x18000a066  sub     rsp, 80h
0x18000a06d  mov     rax, cs:__security_cookie
0x18000a074  xor     rax, rsp
0x18000a077  mov     [rsp+88h+var_10], rax
0x18000a07c  mov     rdi, rdx
0x18000a07f  mov     rbx, rcx
0x18000a082  mov     [rsp+88h+var_58], rcx
0x18000a087  xor     eax, eax
0x18000a089  mov     [rsp+88h+var_64], ax
0x18000a08e  mov     [rsp+88h+var_68], ax
0x18000a093  call    cs:__imp_GetCurrentProcess
0x18000a099  mov     rcx, rax
0x18000a09c  lea     r8, [rsp+88h+var_68]
0x18000a0a1  lea     rdx, [rsp+88h+var_64]
0x18000a0a6  call    cs:__imp_IsWow64Process2
0x18000a0ac  test    eax, eax
0x18000a0ae  jz      loc_18000A13B
0x18000a0b4  xor     eax, eax
0x18000a0b6  movzx   ecx, [rsp+88h+var_68]
0x18000a0bb  cmp     ax, cx
0x18000a0be  jz      short loc_18000A13B
0x18000a0c0  mov     eax, 8664h
0x18000a0c5  cmp     ax, cx
0x18000a0c8  jz      short loc_18000A13B
0x18000a0ca  mov     edx, ecx
0x18000a0cc  lea     rcx, [rsp+88h+var_30]
0x18000a0d1  call    ?GetArchFolderFromMachine@Utility@uus@@SA?AVpath@filesystem@std@@I@Z; uus::Utility::GetArchFolderFromMachine(uint)
0x18000a0d6  nop
0x18000a0d7  mov     r8, rax; this
0x18000a0da  mov     rdx, rdi; struct std::filesystem::path *
0x18000a0dd  lea     rcx, [rsp+88h+Src]; Src
0x18000a0e2  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18000a0e7  xorps   xmm0, xmm0
0x18000a0ea  movups  xmmword ptr [rbx], xmm0
0x18000a0ed  mov     qword ptr [rbx+10h], 0
0x18000a0f5  mov     qword ptr [rbx+18h], 0
0x18000a0fd  movups  xmm0, xmmword ptr [rax]
0x18000a100  movups  xmmword ptr [rbx], xmm0
0x18000a103  movups  xmm1, xmmword ptr [rax+10h]
0x18000a107  movups  xmmword ptr [rbx+10h], xmm1
0x18000a10b  mov     qword ptr [rax+10h], 0
0x18000a113  mov     qword ptr [rax+18h], 7
0x18000a11b  xor     ecx, ecx
0x18000a11d  mov     [rax], cx
0x18000a120  mov     byte ptr [rbx+20h], 1
0x18000a124  lea     rcx, [rsp+88h+Src]
0x18000a129  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a12e  nop
0x18000a12f  lea     rcx, [rsp+88h+var_30]
0x18000a134  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a139  jmp     short loc_18000A13F
0x18000a13b  mov     byte ptr [rbx+20h], 0
0x18000a13f  mov     rax, rbx
0x18000a142  mov     rcx, [rsp+88h+var_10]
0x18000a147  xor     rcx, rsp; StackCookie
0x18000a14a  call    __security_check_cookie
0x18000a14f  mov     rbx, [rsp+88h+arg_10]
0x18000a157  add     rsp, 80h
0x18000a15e  pop     rdi
0x18000a15f  retn
```
