# CAxInstaller::DownloadFileUsingWinHttp(ushort *,ushort *,ulong,ulong)

- ea: `0x180006518`
- end: `0x180006630`
- name: `?DownloadFileUsingWinHttp@CAxInstaller@@AEAAJPEAG0KK@Z`
- size: `280`
- prototype: `int(CAxInstaller *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x180005ee0`

## callees

- `0x1800017c0`
- `0x180006518`
- `0x18000725c`
- `0x180012408`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000661a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000661a`

## pseudocode

```c
__int64 __fastcall CAxInstaller::DownloadFileUsingWinHttp(
        CAxInstaller *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5)
{
  char *v8; // rax
  void (__fastcall ***v9)(_QWORD, __int64); // rdi
  __int64 v10; // rcx
  int v11; // esi
  DWORD v13; // [rsp+20h] [rbp-38h]

  AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 4u, L"DownloadFileUsingWinHttp called");
  *a3 = 0;
  v8 = (char *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = (void (__fastcall ***)(_QWORD, __int64))v8;
  if ( v8 )
  {
    v10 = *((_QWORD *)this + 85);
    *(_QWORD *)v8 = &WinHttpDownload::`vftable';
    *((_QWORD *)v8 + 1) = v10;
    *((_QWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 7) = 0;
    *((_QWORD *)v8 + 8) = 0;
    *((_QWORD *)v8 + 9) = 0;
    *((_QWORD *)v8 + 5) = 0;
    *((_QWORD *)v8 + 4) = 0;
    *((_QWORD *)v8 + 6) = 0;
    *((_QWORD *)v8 + 10) = -1;
    *(_OWORD *)(v8 + 88) = 0;
    *((_QWORD *)v8 + 13) = 0;
    *((_DWORD *)v8 + 28) = 0;
    *((_DWORD *)v8 + 32) = 0;
    v11 = WinHttpDownload::DownloadFile((WinHttpDownload *)v8, a2, (const unsigned __int16 *)this + 36, a3, v13, a5);
    (**v9)(v9, 1);
    if ( v11 >= 0 )
      return (unsigned int)v11;
  }
  else
  {
    v11 = -2147024882;
  }
  if ( *a3 )
  {
    DeleteFileW(a3);
    *a3 = 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006518  push    rbx
0x18000651a  push    rbp
0x18000651b  push    rsi
0x18000651c  push    rdi
0x18000651d  sub     rsp, 38h
0x180006521  mov     rbp, rdx
0x180006524  lea     r9, aDownloadfileus; "DownloadFileUsingWinHttp called"
0x18000652b  mov     edx, 8; unsigned int
0x180006530  mov     rbx, r8
0x180006533  mov     rsi, rcx
0x180006536  lea     rcx, qword_180021AD8; this
0x18000653d  lea     r8d, [rdx-4]; unsigned __int8
0x180006541  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180006546  xor     eax, eax
0x180006548  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000654f  mov     ecx, 88h; unsigned __int64
0x180006554  mov     [rbx], ax
0x180006557  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000655c  mov     rdi, rax
0x18000655f  test    rax, rax
0x180006562  jz      loc_18000660B
0x180006568  mov     rcx, [rsi+2A8h]
0x18000656f  lea     rax, ??_7WinHttpDownload@@6B@; const WinHttpDownload::`vftable'
0x180006576  mov     [rdi], rax
0x180006579  lea     r8, [rsi+48h]; unsigned __int16 *
0x18000657d  xor     eax, eax
0x18000657f  mov     [rdi+8], rcx
0x180006583  mov     qword ptr [rdi+10h], 0
0x18000658b  xorps   xmm0, xmm0
0x18000658e  mov     qword ptr [rdi+38h], 0
0x180006596  mov     r9, rbx; unsigned __int16 *
0x180006599  mov     qword ptr [rdi+40h], 0
0x1800065a1  mov     rdx, rbp; Src
0x1800065a4  mov     qword ptr [rdi+48h], 0
0x1800065ac  mov     rcx, rdi; this
0x1800065af  mov     qword ptr [rdi+28h], 0
0x1800065b7  mov     qword ptr [rdi+20h], 0
0x1800065bf  mov     qword ptr [rdi+30h], 0
0x1800065c7  mov     qword ptr [rdi+50h], 0FFFFFFFFFFFFFFFFh
0x1800065cf  movups  xmmword ptr [rdi+58h], xmm0
0x1800065d3  mov     [rdi+68h], rax
0x1800065d7  mov     [rdi+70h], eax
0x1800065da  mov     [rdi+80h], eax
0x1800065e0  mov     eax, [rsp+58h+arg_20]
0x1800065e7  mov     [rsp+58h+var_30], eax; unsigned int
0x1800065eb  call    ?DownloadFile@WinHttpDownload@@QEAAJPEBG0PEAGKK@Z; WinHttpDownload::DownloadFile(ushort const *,ushort const *,ushort *,ulong,ulong)
0x1800065f0  mov     esi, eax
0x1800065f2  mov     edx, 1
0x1800065f7  mov     rax, [rdi]
0x1800065fa  mov     rcx, rdi
0x1800065fd  mov     rax, [rax]
0x180006600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006605  test    esi, esi
0x180006607  jns     short loc_180006625
0x180006609  jmp     short loc_180006610
0x18000660b  mov     esi, 8007000Eh
0x180006610  xor     ecx, ecx
0x180006612  cmp     cx, [rbx]
0x180006615  jz      short loc_180006625
0x180006617  mov     rcx, rbx; lpFileName
0x18000661a  call    cs:__imp_DeleteFileW
0x180006620  xor     ecx, ecx
0x180006622  mov     [rbx], cx
0x180006625  mov     eax, esi
0x180006627  add     rsp, 38h
0x18000662b  pop     rdi
0x18000662c  pop     rsi
0x18000662d  pop     rbp
0x18000662e  pop     rbx
0x18000662f  retn
```
