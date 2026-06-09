# File::Verify(ConfigSettings const &)

- ea: `0x1800274b0`
- end: `0x180027722`
- name: `?Verify@File@@QEAA?AW4FileVerifyStatus@@AEBVConfigSettings@@@Z`
- size: `626`
- prototype: `__int64 __fastcall(File *, const struct ConfigSettings *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180031a40`

## callees

- `0x18001301c`
- `0x1800197d4`
- `0x1800274b0`
- `0x180027728`
- `0x18004ebd4`
- `0x18004fb1c`
- `0x1800512b4`
- `0x180130010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002755e`
- `KERNEL32!CreateFileW` at `0x18002755e`
- `KERNEL32!CloseHandle` at `0x180027717`
- `KERNEL32!CloseHandle` at `0x180027717`
- `KERNEL32!GetLastError` at `0x18002757b`
- `KERNEL32!GetLastError` at `0x18002757b`

## string_xrefs

- `0x1800275e4`: `FilePathHash invalid(%ls)`
- `0x1800275a5`: `CreateFileW(%ls) failed [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall File::Verify(File *a1, const struct ConfigSettings *a2)
{
  __int64 FileW; // rbx
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 v7; // rax
  unsigned int v8; // esi
  __int64 Usn; // rax
  __int64 v10; // rcx
  char v11; // r14

  FileW = -1;
  v5 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 8LL))(a1);
  v6 = std::wstring::find(v5, 124);
  if ( v6 == -1
    || (unsigned __int64)(*(_QWORD *)((*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 8LL))(a1) + 16) - v6) < 0xE )
  {
    (*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 8LL))(a1);
    AslLogCallPrintf(3, (unsigned int)"File::Verify", 2283, (unsigned int)"FilePathHash invalid(%ls)");
    goto LABEL_8;
  }
  v7 = (*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 24LL))(a1);
  if ( *(_QWORD *)(v7 + 24) > 7u )
    v7 = *(_QWORD *)v7;
  FileW = (__int64)CreateFileW((LPCWSTR)v7, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    GetLastError();
    (*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 24LL))(a1);
    AslLogCallPrintf(3, (unsigned int)"File::Verify", 2294, (unsigned int)"CreateFileW(%ls) failed [%d]");
LABEL_8:
    File::RemoveFileFromCache(a1, a2);
    v8 = 2;
    goto LABEL_13;
  }
  v8 = 0;
  Usn = File::QueryUsn((HANDLE)FileW, 0);
  v10 = *((_QWORD *)a1 + 99);
  if ( Usn == v10 )
  {
    v11 = 0;
  }
  else
  {
    v11 = 1;
    if ( v10 )
    {
      (*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 24LL))(a1);
      AslLogCallPrintf(3, (unsigned int)"File::Verify", 2315, (unsigned int)"File changed, updating %ls");
      File::SetFileAttributesW(a1, 1073878285, 0);
      v8 = 1;
    }
    else
    {
      *((_QWORD *)a1 + 99) = Usn;
    }
  }
  if ( *(_QWORD *)((*(__int64 (__fastcall **)(File *))(*(_QWORD *)a1 + 16LL))(a1) + 16) )
  {
    if ( !v11 )
      goto LABEL_13;
  }
  else
  {
    File::SetFileAttributesW(a1, 1073878285, 0);
    v8 = 3;
  }
  File::SaveFileToCache(a1, a2);
LABEL_13:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  return v8;
}

```

## disassembly

```asm
0x1800274b0  mov     rax, rsp
0x1800274b3  push    rdi
0x1800274b4  push    r14
0x1800274b6  push    r15
0x1800274b8  sub     rsp, 50h
0x1800274bc  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800274c4  mov     [rax+10h], rbx
0x1800274c8  mov     [rax+18h], rsi
0x1800274cc  mov     r15, rdx
0x1800274cf  mov     rdi, rcx
0x1800274d2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800274d6  mov     [rax+8], rbx
0x1800274da  mov     rax, [rcx]
0x1800274dd  mov     rax, [rax+8]
0x1800274e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274e6  lea     edx, [rbx+7Dh]
0x1800274e9  mov     rcx, rax
0x1800274ec  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x1800274f1  mov     rsi, rax
0x1800274f4  cmp     rax, rbx
0x1800274f7  jz      loc_1800275C5
0x1800274fd  mov     rcx, [rdi]
0x180027500  mov     rax, [rcx+8]
0x180027504  mov     rcx, rdi
0x180027507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002750c  mov     rcx, [rax+10h]
0x180027510  sub     rcx, rsi
0x180027513  cmp     rcx, 0Eh
0x180027517  jb      loc_1800275C5
0x18002751d  mov     rax, [rdi]
0x180027520  mov     rcx, rdi
0x180027523  mov     rax, [rax+18h]
0x180027527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002752c  cmp     qword ptr [rax+18h], 7
0x180027531  jbe     short loc_180027536
0x180027533  mov     rax, [rax]
0x180027536  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18002753f  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180027547  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18002754f  xor     r9d, r9d; lpSecurityAttributes
0x180027552  mov     edx, 80000000h; dwDesiredAccess
0x180027557  lea     r8d, [r9+7]; dwShareMode
0x18002755b  mov     rcx, rax; lpFileName
0x18002755e  call    cs:__imp_CreateFileW
0x180027564  mov     rbx, rax
0x180027567  mov     [rsp+68h+arg_0], rax
0x18002756c  inc     rax
0x18002756f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180027575  jnz     loc_180027614
0x18002757b  call    cs:__imp_GetLastError
0x180027581  mov     esi, eax
0x180027583  mov     rcx, [rdi]
0x180027586  mov     rax, [rcx+18h]
0x18002758a  mov     rcx, rdi
0x18002758d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027592  cmp     qword ptr [rax+18h], 7
0x180027597  jbe     short loc_18002759C
0x180027599  mov     rax, [rax]
0x18002759c  mov     [rsp+68h+dwFlagsAndAttributes], esi
0x1800275a0  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x1800275a5  lea     r9, aCreatefilewLsF; "CreateFileW(%ls) failed [%d]"
0x1800275ac  mov     r8d, 8F6h
0x1800275b2  lea     rdx, aFileVerify; "File::Verify"
0x1800275b9  mov     ecx, 3
0x1800275be  call    AslLogCallPrintf
0x1800275c3  jmp     short loc_180027602
0x1800275c5  mov     rax, [rdi]
0x1800275c8  mov     rcx, rdi
0x1800275cb  mov     rax, [rax+8]
0x1800275cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275d4  cmp     qword ptr [rax+18h], 7
0x1800275d9  ja      loc_18002767C
0x1800275df  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x1800275e4  lea     r9, aFilepathhashIn; "FilePathHash invalid(%ls)"
0x1800275eb  mov     r8d, 8EBh
0x1800275f1  lea     rdx, aFileVerify; "File::Verify"
0x1800275f8  mov     ecx, 3
0x1800275fd  call    AslLogCallPrintf
0x180027602  mov     rdx, r15; struct ConfigSettings *
0x180027605  mov     rcx, rdi; this
0x180027608  call    ?RemoveFileFromCache@File@@QEAAXAEBVConfigSettings@@@Z; File::RemoveFileFromCache(ConfigSettings const &)
0x18002760d  mov     esi, 2
0x180027612  jmp     short loc_180027656
0x180027614  xor     esi, esi
0x180027616  xor     edx, edx; lpFileName
0x180027618  mov     rcx, rbx; hDevice
0x18002761b  call    ?QueryUsn@File@@SA_JPEAXPEBG@Z; File::QueryUsn(void *,ushort const *)
0x180027620  mov     rcx, [rdi+318h]
0x180027627  cmp     rax, rcx
0x18002762a  jnz     loc_1800276D8
0x180027630  xor     r14b, r14b
0x180027633  mov     rax, [rdi]
0x180027636  mov     rcx, rdi
0x180027639  mov     rax, [rax+10h]
0x18002763d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027642  cmp     qword ptr [rax+10h], 0
0x180027647  jz      loc_1800276EF
0x18002764d  test    r14b, r14b
0x180027650  jnz     loc_180027704
0x180027656  lea     rcx, [rbx-1]
0x18002765a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002765e  jbe     loc_180027714
0x180027664  mov     eax, esi
0x180027666  lea     r11, [rsp+68h+var_18]
0x18002766b  mov     rbx, [r11+28h]
0x18002766f  mov     rsi, [r11+30h]
0x180027673  mov     rsp, r11
0x180027676  pop     r15
0x180027678  pop     r14
0x18002767a  pop     rdi
0x18002767b  retn
0x18002767c  mov     rax, [rax]
0x18002767f  jmp     loc_1800275DF
0x180027684  mov     rax, [rdi]
0x180027687  mov     rcx, rdi
0x18002768a  mov     rax, [rax+18h]
0x18002768e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027693  cmp     qword ptr [rax+18h], 7
0x180027698  jbe     short loc_18002769D
0x18002769a  mov     rax, [rax]
0x18002769d  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x1800276a2  lea     r9, aFileChangedUpd; "File changed, updating %ls"
0x1800276a9  mov     r8d, 90Bh
0x1800276af  lea     rdx, aFileVerify; "File::Verify"
0x1800276b6  mov     ecx, 3
0x1800276bb  call    AslLogCallPrintf
0x1800276c0  xor     r8d, r8d; bool
0x1800276c3  mov     edx, 4002150Dh; unsigned __int64
0x1800276c8  mov     rcx, rdi; this
0x1800276cb  call    ?SetFileAttributesW@File@@QEAAX_K_N@Z; File::SetFileAttributesW(unsigned __int64,bool)
0x1800276d0  mov     esi, r14d
0x1800276d3  jmp     loc_180027633
0x1800276d8  mov     r14d, 1
0x1800276de  test    rcx, rcx
0x1800276e1  jnz     short loc_180027684
0x1800276e3  mov     [rdi+318h], rax
0x1800276ea  jmp     loc_180027633
0x1800276ef  xor     r8d, r8d; bool
0x1800276f2  mov     edx, 4002150Dh; unsigned __int64
0x1800276f7  mov     rcx, rdi; this
0x1800276fa  call    ?SetFileAttributesW@File@@QEAAX_K_N@Z; File::SetFileAttributesW(unsigned __int64,bool)
0x1800276ff  mov     esi, 3
0x180027704  mov     rdx, r15; struct ConfigSettings *
0x180027707  mov     rcx, rdi; this
0x18002770a  call    ?SaveFileToCache@File@@QEAAXAEBVConfigSettings@@@Z; File::SaveFileToCache(ConfigSettings const &)
0x18002770f  jmp     loc_180027656
0x180027714  mov     rcx, rbx; hObject
0x180027717  call    cs:__imp_CloseHandle
0x18002771d  jmp     loc_180027664
```
