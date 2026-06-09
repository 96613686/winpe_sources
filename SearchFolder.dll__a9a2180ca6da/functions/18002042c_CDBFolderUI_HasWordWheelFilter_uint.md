# CDBFolderUI::_HasWordWheelFilter(uint *)

- ea: `0x18002042c`
- end: `0x1800205d7`
- name: `?_HasWordWheelFilter@CDBFolderUI@@AEAAHPEAI@Z`
- size: `427`
- prototype: `_BOOL8 __fastcall(CDBFolderUI *this, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001fd38`

## callees

- `0x1800033d0`
- `0x1800045d0`
- `0x180004640`
- `0x180004a10`
- `0x180005460`
- `0x18002042c`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x180020525`
- `SHELL32!__imp_ILFindLastID` at `0x180020525`
- `SHELL32!__imp_ILRemoveLastID` at `0x180020584`
- `SHELL32!__imp_ILRemoveLastID` at `0x180020584`

## pseudocode

```c
_BOOL8 __fastcall CDBFolderUI::_HasWordWheelFilter(CDBFolderUI *this, unsigned int *a2)
{
  __int64 (__fastcall ****v3)(_QWORD, GUID *, __int64 *); // rbx
  int v4; // eax
  BOOL v5; // esi
  int v6; // eax
  int v7; // eax
  int v8; // r14d
  int v9; // r15d
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, LPITEMIDLIST, GUID *, __int64 *); // rbx
  LPITEMIDLIST ID; // rax
  int v14; // [rsp+20h] [rbp-28h]
  __int64 v15[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  int v17; // [rsp+90h] [rbp+48h] BYREF
  LPCITEMIDLIST pidl; // [rsp+98h] [rbp+50h] BYREF
  __int64 v19; // [rsp+A0h] [rbp+58h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+60h] BYREF

  *a2 = 0;
  v15[0] = 0;
  v3 = (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))((char *)this + 24);
  v4 = Microsoft::WRL::ComPtr<IShellFolder3>::As<IDBFolderForUIPriv>(
         (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3,
         v15);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v19 = 0;
    v6 = Microsoft::WRL::ComPtr<IShellFolder3>::As<IPersistFolder2>(v3, &v19);
    v5 = v6;
    if ( v6 >= 0 )
    {
      pidl = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, LPCITEMIDLIST *))(*(_QWORD *)v19 + 40LL))(v19, &pidl);
      v5 = v7;
      if ( v7 >= 0 )
      {
        v5 = 0;
        v8 = 0;
        v9 = 0;
        do
        {
          if ( v5 )
            goto LABEL_18;
          if ( !pidl || !pidl->mkid.cb )
            break;
          v20 = 0;
          v10 = v15[0];
          v11 = *(int (__fastcall **)(__int64, LPITEMIDLIST, GUID *, __int64 *))(*(_QWORD *)v15[0] + 64LL);
          ID = ILFindLastID(pidl);
          if ( v11(v10, ID, &GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea, &v20) >= 0 )
          {
            v17 = 0;
            v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 72LL))(v20, &v17);
            if ( v8 >= 0 )
              v5 = (v17 & 1) != 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          ILRemoveLastID((LPITEMIDLIST)pidl);
          ++v9;
        }
        while ( v8 >= 0 );
        if ( v8 >= 0 && v5 )
LABEL_18:
          *a2 = v9 - 1;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B0,
          (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
          (const char *)(unsigned int)v7,
          v14);
      }
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pidl);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5AE,
        (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
        (const char *)(unsigned int)v6,
        v14);
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v19);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5AB,
      (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
      (const char *)(unsigned int)v4,
      v14);
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v15);
  return v5;
}

```

## disassembly

```asm
0x18002042c  push    rbp
0x18002042e  push    rbx
0x18002042f  push    rsi
0x180020430  push    rdi
0x180020431  push    r12
0x180020433  push    r13
0x180020435  push    r14
0x180020437  push    r15
0x180020439  mov     rbp, rsp
0x18002043c  sub     rsp, 48h
0x180020440  mov     r12, rdx
0x180020443  xor     r13d, r13d
0x180020446  mov     [rdx], r13d
0x180020449  mov     [rbp+var_18], r13
0x18002044d  lea     rbx, [rcx+18h]
0x180020451  lea     rdx, [rbp+var_18]
0x180020455  mov     rcx, rbx
0x180020458  call    ??$As@UIDBFolderForUIPriv@@@?$ComPtr@UIShellFolder3@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDBFolderForUIPriv@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IShellFolder3>::As<IDBFolderForUIPriv>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDBFolderForUIPriv>>)
0x18002045d  mov     esi, eax
0x18002045f  test    eax, eax
0x180020461  jns     short loc_180020480
0x180020463  mov     rcx, [rbp+40h]; this
0x180020467  mov     r9d, eax; char *
0x18002046a  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x180020471  mov     edx, 5ABh; void *
0x180020476  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002047b  jmp     loc_1800205BB
0x180020480  mov     [rbp+arg_10], r13
0x180020484  lea     rdx, [rbp+arg_10]
0x180020488  mov     rcx, rbx
0x18002048b  call    ??$As@UIPersistFolder2@@@?$ComPtr@UIShellFolder3@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPersistFolder2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IShellFolder3>::As<IPersistFolder2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IPersistFolder2>>)
0x180020490  mov     esi, eax
0x180020492  test    eax, eax
0x180020494  jns     short loc_1800204B3
0x180020496  mov     rcx, [rbp+40h]; this
0x18002049a  mov     r9d, eax; char *
0x18002049d  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x1800204a4  mov     edx, 5AEh; void *
0x1800204a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800204ae  jmp     loc_1800205B1
0x1800204b3  mov     [rbp+pidl], r13
0x1800204b7  mov     rcx, [rbp+arg_10]
0x1800204bb  mov     rax, [rcx]
0x1800204be  lea     rdx, [rbp+pidl]
0x1800204c2  mov     rax, [rax+28h]
0x1800204c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204cb  mov     esi, eax
0x1800204cd  test    eax, eax
0x1800204cf  jns     short loc_1800204EE
0x1800204d1  mov     rcx, [rbp+40h]; this
0x1800204d5  mov     r9d, eax; char *
0x1800204d8  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x1800204df  mov     edx, 5B0h; void *
0x1800204e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800204e9  jmp     loc_1800205A7
0x1800204ee  mov     esi, r13d
0x1800204f1  mov     r14d, r13d
0x1800204f4  mov     r15d, r13d
0x1800204f7  test    esi, esi
0x1800204f9  jnz     loc_18002059F
0x1800204ff  mov     rcx, [rbp+pidl]; pidl
0x180020503  test    rcx, rcx
0x180020506  jz      loc_180020596
0x18002050c  cmp     [rcx], r13w
0x180020510  jz      loc_180020596
0x180020516  mov     [rbp+arg_18], r13
0x18002051a  mov     rdi, [rbp+var_18]
0x18002051e  mov     rax, [rdi]
0x180020521  mov     rbx, [rax+40h]
0x180020525  call    cs:__imp_ILFindLastID
0x18002052b  lea     r9, [rbp+arg_18]
0x18002052f  lea     r8, _GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea
0x180020536  mov     rdx, rax
0x180020539  mov     rcx, rdi
0x18002053c  mov     rax, rbx
0x18002053f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020544  test    eax, eax
0x180020546  js      short loc_180020580
0x180020548  mov     [rbp+arg_0], r13d
0x18002054c  mov     rcx, [rbp+arg_18]
0x180020550  mov     rax, [rcx]
0x180020553  lea     rdx, [rbp+arg_0]
0x180020557  mov     rax, [rax+48h]
0x18002055b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020560  mov     r14d, eax
0x180020563  test    eax, eax
0x180020565  js      short loc_180020570
0x180020567  lea     eax, [rsi+1]
0x18002056a  test    byte ptr [rbp+arg_0], al
0x18002056d  cmovnz  esi, eax
0x180020570  mov     rcx, [rbp+arg_18]
0x180020574  mov     rdx, [rcx]
0x180020577  mov     rax, [rdx+10h]
0x18002057b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020580  mov     rcx, [rbp+pidl]; pidl
0x180020584  call    cs:__imp_ILRemoveLastID
0x18002058a  inc     r15d
0x18002058d  test    r14d, r14d
0x180020590  jns     loc_1800204F7
0x180020596  test    r14d, r14d
0x180020599  js      short loc_1800205A7
0x18002059b  test    esi, esi
0x18002059d  jz      short loc_1800205A7
0x18002059f  lea     eax, [r15-1]
0x1800205a3  mov     [r12], eax
0x1800205a7  lea     rcx, [rbp+pidl]; void *
0x1800205ab  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800205b0  nop
0x1800205b1  lea     rcx, [rbp+arg_10]
0x1800205b5  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800205ba  nop
0x1800205bb  lea     rcx, [rbp+var_18]
0x1800205bf  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800205c4  mov     eax, esi
0x1800205c6  add     rsp, 48h
0x1800205ca  pop     r15
0x1800205cc  pop     r14
0x1800205ce  pop     r13
0x1800205d0  pop     r12
0x1800205d2  pop     rdi
0x1800205d3  pop     rsi
0x1800205d4  pop     rbx
0x1800205d5  pop     rbp
0x1800205d6  retn
```
