# LanguagePacksUninstaller::LanguagePacksUninstaller(CbsLanguageSession const &)

- ea: `0x180024090`
- end: `0x180024192`
- name: `??0LanguagePacksUninstaller@@QEAA@AEBVCbsLanguageSession@@@Z`
- size: `258`
- prototype: `LanguagePacksUninstaller *__fastcall(LanguagePacksUninstaller *__hidden this, const struct CbsLanguageSession *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180013e1c`
- `0x180014788`

## callees

- `0x180004118`
- `0x180024090`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800240f2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800240f2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800240e4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800240e4`

## string_xrefs

- `0x1800240bc`: `UpdateAPI.dll`

## pseudocode

```c
LanguagePacksUninstaller *__fastcall LanguagePacksUninstaller::LanguagePacksUninstaller(
        LanguagePacksUninstaller *this,
        const struct CbsLanguageSession *a2)
{
  HMODULE LibraryW; // rax

  memset_0((char *)this + 16, 0, 0xC0u);
  *((_QWORD *)this + 1) = L"LanguageFeaturesOnDemand";
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  LibraryW = LoadLibraryW(L"UpdateAPI.dll");
  if ( LibraryW )
  {
    FreeLibrary(LibraryW);
    LODWORD(LibraryW) = 1;
  }
  *(_DWORD *)this = (_DWORD)LibraryW;
  *(_OWORD *)((char *)this + 8) = *(_OWORD *)a2;
  *(_OWORD *)((char *)this + 24) = *((_OWORD *)a2 + 1);
  *(_OWORD *)((char *)this + 40) = *((_OWORD *)a2 + 2);
  *(_OWORD *)((char *)this + 56) = *((_OWORD *)a2 + 3);
  *(_OWORD *)((char *)this + 72) = *((_OWORD *)a2 + 4);
  *(_OWORD *)((char *)this + 88) = *((_OWORD *)a2 + 5);
  *(_OWORD *)((char *)this + 104) = *((_OWORD *)a2 + 6);
  *(_OWORD *)((char *)this + 120) = *((_OWORD *)a2 + 7);
  *(_OWORD *)((char *)this + 136) = *((_OWORD *)a2 + 8);
  *(_OWORD *)((char *)this + 152) = *((_OWORD *)a2 + 9);
  *(_OWORD *)((char *)this + 168) = *((_OWORD *)a2 + 10);
  *(_OWORD *)((char *)this + 184) = *((_OWORD *)a2 + 11);
  *((_QWORD *)this + 25) = *((_QWORD *)a2 + 24);
  return this;
}

```

## disassembly

```asm
0x180024090  mov     [rsp+arg_0], rbx
0x180024095  push    rdi
0x180024096  sub     rsp, 20h
0x18002409a  mov     rdi, rdx
0x18002409d  mov     rbx, rcx
0x1800240a0  add     rcx, 10h; void *
0x1800240a4  xor     edx, edx; Val
0x1800240a6  mov     r8d, 0C0h; Size
0x1800240ac  call    memset_0
0x1800240b1  lea     rax, aLanguagefeatur; "LanguageFeaturesOnDemand"
0x1800240b8  mov     [rbx+8], rax
0x1800240bc  lea     rcx, LibFileName; "UpdateAPI.dll"
0x1800240c3  mov     qword ptr [rbx+0D0h], 0
0x1800240ce  mov     qword ptr [rbx+0D8h], 0
0x1800240d9  mov     qword ptr [rbx+0E0h], 0
0x1800240e4  call    cs:__imp_LoadLibraryW
0x1800240ea  test    rax, rax
0x1800240ed  jz      short loc_1800240FD
0x1800240ef  mov     rcx, rax; hLibModule
0x1800240f2  call    cs:__imp_FreeLibrary
0x1800240f8  mov     eax, 1
0x1800240fd  mov     [rbx], eax
0x1800240ff  movups  xmm0, xmmword ptr [rdi]
0x180024102  movups  xmmword ptr [rbx+8], xmm0
0x180024106  movups  xmm1, xmmword ptr [rdi+10h]
0x18002410a  movups  xmmword ptr [rbx+18h], xmm1
0x18002410e  movups  xmm0, xmmword ptr [rdi+20h]
0x180024112  movups  xmmword ptr [rbx+28h], xmm0
0x180024116  movups  xmm1, xmmword ptr [rdi+30h]
0x18002411a  movups  xmmword ptr [rbx+38h], xmm1
0x18002411e  movups  xmm0, xmmword ptr [rdi+40h]
0x180024122  movups  xmmword ptr [rbx+48h], xmm0
0x180024126  movups  xmm1, xmmword ptr [rdi+50h]
0x18002412a  movups  xmmword ptr [rbx+58h], xmm1
0x18002412e  movups  xmm0, xmmword ptr [rdi+60h]
0x180024132  movups  xmmword ptr [rbx+68h], xmm0
0x180024136  movups  xmm1, xmmword ptr [rdi+70h]
0x18002413a  movups  xmmword ptr [rbx+78h], xmm1
0x18002413e  movups  xmm0, xmmword ptr [rdi+80h]
0x180024145  movups  xmmword ptr [rbx+88h], xmm0
0x18002414c  movups  xmm1, xmmword ptr [rdi+90h]
0x180024153  movups  xmmword ptr [rbx+98h], xmm1
0x18002415a  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180024161  movups  xmmword ptr [rbx+0A8h], xmm0
0x180024168  movups  xmm1, xmmword ptr [rdi+0B0h]
0x18002416f  movups  xmmword ptr [rbx+0B8h], xmm1
0x180024176  mov     rax, [rdi+0C0h]
0x18002417d  mov     [rbx+0C8h], rax
0x180024184  mov     rax, rbx
0x180024187  mov     rbx, [rsp+28h+arg_0]
0x18002418c  add     rsp, 20h
0x180024190  pop     rdi
0x180024191  retn
```
