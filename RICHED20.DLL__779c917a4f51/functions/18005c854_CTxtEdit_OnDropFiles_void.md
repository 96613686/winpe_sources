# CTxtEdit::OnDropFiles(void *)

- ea: `0x18005c854`
- end: `0x18005cb5f`
- name: `?OnDropFiles@CTxtEdit@@AEAA_JPEAX@Z`
- size: `779`
- prototype: `__int64 __fastcall(CTxtEdit *__hidden this, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18002cfd0`

## callees

- `0x180008f80`
- `0x180018ea8`
- `0x18002c900`
- `0x180031974`
- `0x180031a38`
- `0x18003b9a4`
- `0x18003d450`
- `0x18003dfc0`
- `0x18003e774`
- `0x180045778`
- `0x18005c250`
- `0x18005c854`
- `0x18008f8b0`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18005caf0`
- `KERNEL32!MultiByteToWideChar` at `0x18005caf0`
- `KERNEL32!GetProcAddress` at `0x18005c8d3`
- `KERNEL32!GetProcAddress` at `0x18005c8eb`
- `KERNEL32!GetProcAddress` at `0x18005c903`
- `KERNEL32!GetProcAddress` at `0x18005c91b`
- `KERNEL32!GetProcAddress` at `0x18005c8d3`
- `KERNEL32!GetProcAddress` at `0x18005c8eb`
- `KERNEL32!GetProcAddress` at `0x18005c903`
- `KERNEL32!GetProcAddress` at `0x18005c91b`
- `KERNEL32!FreeLibrary` at `0x18005cb2d`
- `KERNEL32!FreeLibrary` at `0x18005cb2d`

## string_xrefs

- `0x18005c8b1`: `Shell32.DLL`

## pseudocode

```c
__int64 __fastcall CTxtEdit::OnDropFiles(CTxtEdit *this, void *a2)
{
  __int64 v4; // rdx
  unsigned int v5; // r8d
  struct CTxtSelection *Sel; // r13
  HINSTANCE Library; // rax
  HMODULE v8; // r15
  FARPROC v9; // rbx
  FARPROC v10; // rsi
  FARPROC v11; // rax
  __int64 (__fastcall *v12)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  unsigned int v13; // r12d
  __int64 v14; // rbx
  int CpFromAcp; // esi
  const struct CCharFormat *CF; // rbx
  int v17; // r8d
  int iCF; // eax
  int v19; // ebx
  bool v20; // zf
  int v21; // r8d
  unsigned int v22; // ebx
  void (__fastcall *v23)(_QWORD, _QWORD, _QWORD, _QWORD); // r13
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  const struct CCharFormat *CharFormat; // [rsp+58h] [rbp-A8h]
  INT_PTR (__stdcall *v27)(); // [rsp+60h] [rbp-A0h]
  FARPROC v28; // [rsp+68h] [rbp-98h]
  FARPROC ProcAddress; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  __int128 v31; // [rsp+80h] [rbp-80h]
  void *v32; // [rsp+90h] [rbp-70h]
  int v33[2]; // [rsp+98h] [rbp-68h]
  _BYTE v34[32]; // [rsp+A0h] [rbp-60h] BYREF
  int v35; // [rsp+C0h] [rbp-40h]
  CHAR MultiByteStr[272]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR WideCharStr[264]; // [rsp+200h] [rbp+100h] BYREF

  v25 = 0;
  Sel = CTxtEdit::GetSel(this);
  if ( Sel )
  {
    if ( (*((_BYTE *)this + 180) & 4) == 0 )
    {
      Library = CW32System::LoadLibrary(L"Shell32.DLL", v4, v5);
      v8 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "DragFinish");
        v9 = GetProcAddress(v8, "DragQueryFileA");
        v28 = v9;
        v10 = GetProcAddress(v8, "DragQueryFileW");
        v27 = v10;
        v11 = GetProcAddress(v8, "DragQueryPoint");
        if ( !ProcAddress || !v9 || !v10 || !v11 )
          goto LABEL_30;
        ((void (__fastcall *)(void *, __int64 *))v11)(a2, &v25);
        v12 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v9;
        if ( CW32System::_dwPlatformId != 1 )
          v12 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v10;
        v13 = v12(a2, 0xFFFFFFFFLL, 0, 0);
        if ( v13 )
        {
          v14 = v25;
          CRchTxtPtr::CRchTxtPtr((CRchTxtPtr *)v34, this);
          if ( (*(int (__fastcall **)(_QWORD, __int64, _QWORD, _BYTE *, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 232LL))(
                 *((_QWORD *)this + 8),
                 v14,
                 0,
                 v34,
                 0,
                 0,
                 0,
                 0,
                 0) < 0 )
          {
            iCF = CTxtRange::Get_iCF(Sel);
            CpFromAcp = *((_DWORD *)Sel + 10);
            v19 = iCF;
            CharFormat = CTxtArray::GetCharFormat((CTxtEdit *)((char *)this + 248), iCF);
            ReleaseFormats(v19, -1);
            CF = CharFormat;
          }
          else
          {
            CpFromAcp = v35;
            CF = CRchTxtPtr::GetCF((CRchTxtPtr *)v34);
          }
          if ( (*((_DWORD *)this + 44) & 0x100000) != 0 )
          {
            v20 = (*((_DWORD *)this + 45) & 0x80000) == 0;
            v31 = 0;
            v30 = 0;
            *(_QWORD *)v33 = 0;
            v32 = a2;
            if ( v20 )
              v33[0] = CpFromAcp;
            else
              v33[0] = CTxtEdit::GetAcpFromCp(this, CpFromAcp, v17);
            v33[1] = (*(unsigned __int8 *)CF >> 4) & 1;
            if ( (unsigned int)CTxtEdit::TxNotify(this, 0x703u, &v30) )
            {
LABEL_29:
              ((void (__fastcall *)(void *))ProcAddress)(a2);
LABEL_30:
              FreeLibrary(v8);
              return 0;
            }
            if ( (*((_DWORD *)this + 45) & 0x80000) != 0 )
              CpFromAcp = CTxtEdit::GetCpFromAcp(this, v33[0], v21);
            else
              CpFromAcp = v33[0];
          }
          CTxtRange::SetCp(Sel, CpFromAcp);
          v10 = v27;
        }
        v22 = 0;
        if ( v13 )
        {
          v23 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v28;
          do
          {
            if ( CW32System::_dwPlatformId == 1 )
            {
              v23(a2, v22, MultiByteStr, 260);
              MultiByteToWideChar(0, 0, MultiByteStr, -1, WideCharStr, 260);
            }
            else
            {
              ((void (__fastcall *)(void *, _QWORD, WCHAR *, __int64))v10)(a2, v22, WideCharStr, 260);
            }
            CTxtEdit::InsertFromFile(this, WideCharStr);
            ++v22;
          }
          while ( v22 < v13 );
        }
        goto LABEL_29;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005c854  mov     [rsp-8+arg_10], rbx
0x18005c859  push    rbp
0x18005c85a  push    rsi
0x18005c85b  push    rdi
0x18005c85c  push    r12
0x18005c85e  push    r13
0x18005c860  push    r14
0x18005c862  push    r15
0x18005c864  lea     rbp, [rsp-320h]
0x18005c86c  sub     rsp, 420h
0x18005c873  mov     rax, cs:__security_cookie
0x18005c87a  xor     rax, rsp
0x18005c87d  mov     [rbp+350h+var_40], rax
0x18005c884  mov     r14, rdx
0x18005c887  mov     [rsp+450h+var_400], 0
0x18005c890  mov     rdi, rcx
0x18005c893  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x18005c898  mov     r13, rax
0x18005c89b  test    rax, rax
0x18005c89e  jz      loc_18005CB33
0x18005c8a4  test    byte ptr [rdi+0B4h], 4
0x18005c8ab  jnz     loc_18005CB33
0x18005c8b1  lea     rcx, aShell32Dll; "Shell32.DLL"
0x18005c8b8  call    ?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z; CW32System::LoadLibrary(ushort const *)
0x18005c8bd  mov     r15, rax
0x18005c8c0  test    rax, rax
0x18005c8c3  jz      loc_18005CB33
0x18005c8c9  lea     rdx, aDragfinish; "DragFinish"
0x18005c8d0  mov     rcx, rax; hModule
0x18005c8d3  call    cs:__imp_GetProcAddress
0x18005c8d9  lea     rdx, aDragqueryfilea; "DragQueryFileA"
0x18005c8e0  mov     rcx, r15; hModule
0x18005c8e3  mov     r12, rax
0x18005c8e6  mov     [rsp+450h+var_3E0], rax
0x18005c8eb  call    cs:__imp_GetProcAddress
0x18005c8f1  lea     rdx, aDragqueryfilew; "DragQueryFileW"
0x18005c8f8  mov     rcx, r15; hModule
0x18005c8fb  mov     rbx, rax
0x18005c8fe  mov     [rsp+450h+var_3E8], rax
0x18005c903  call    cs:__imp_GetProcAddress
0x18005c909  lea     rdx, aDragquerypoint; "DragQueryPoint"
0x18005c910  mov     rcx, r15; hModule
0x18005c913  mov     rsi, rax
0x18005c916  mov     [rsp+450h+var_3F0], rax
0x18005c91b  call    cs:__imp_GetProcAddress
0x18005c921  test    r12, r12
0x18005c924  jz      loc_18005CB2A
0x18005c92a  test    rbx, rbx
0x18005c92d  jz      loc_18005CB2A
0x18005c933  test    rsi, rsi
0x18005c936  jz      loc_18005CB2A
0x18005c93c  test    rax, rax
0x18005c93f  jz      loc_18005CB2A
0x18005c945  lea     rdx, [rsp+450h+var_400]
0x18005c94a  mov     rcx, r14
0x18005c94d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c952  xor     r9d, r9d
0x18005c955  xor     r8d, r8d
0x18005c958  or      edx, 0FFFFFFFFh
0x18005c95b  mov     rcx, r14
0x18005c95e  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18005c965  mov     rax, rbx
0x18005c968  jz      short loc_18005C96D
0x18005c96a  mov     rax, rsi
0x18005c96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c972  mov     r12d, eax
0x18005c975  test    eax, eax
0x18005c977  jz      loc_18005CAA4
0x18005c97d  mov     rbx, [rsp+450h+var_400]
0x18005c982  lea     rcx, [rbp+350h+var_3B0]; this
0x18005c986  mov     rdx, rdi; struct CTxtEdit *
0x18005c989  call    ??0CRchTxtPtr@@QEAA@PEAVCTxtEdit@@@Z; CRchTxtPtr::CRchTxtPtr(CTxtEdit *)
0x18005c98e  mov     rcx, [rdi+40h]
0x18005c992  lea     r9, [rbp+350h+var_3B0]
0x18005c996  xor     esi, esi
0x18005c998  xor     r8d, r8d
0x18005c99b  mov     [rsp+450h+var_410], rsi
0x18005c9a0  mov     rdx, rbx
0x18005c9a3  mov     [rsp+450h+var_418], rsi
0x18005c9a8  mov     rax, [rcx]
0x18005c9ab  mov     [rsp+450h+var_420], rsi
0x18005c9b0  mov     [rsp+450h+cchWideChar], esi
0x18005c9b4  mov     [rsp+450h+lpWideCharStr], rsi
0x18005c9b9  mov     rax, [rax+0E8h]
0x18005c9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9c5  test    eax, eax
0x18005c9c7  js      short loc_18005C9DA
0x18005c9c9  mov     esi, [rbp+350h+var_390]
0x18005c9cc  lea     rcx, [rbp+350h+var_3B0]; this
0x18005c9d0  call    ?GetCF@CRchTxtPtr@@QEBAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCF(void)
0x18005c9d5  mov     rbx, rax
0x18005c9d8  jmp     short loc_18005CA0A
0x18005c9da  mov     rcx, r13; this
0x18005c9dd  call    ?Get_iCF@CTxtRange@@QEAAJXZ; CTxtRange::Get_iCF(void)
0x18005c9e2  mov     esi, [r13+28h]
0x18005c9e6  lea     rcx, [rdi+0F8h]; this
0x18005c9ed  mov     edx, eax; int
0x18005c9ef  mov     ebx, eax
0x18005c9f1  call    ?GetCharFormat@CTxtArray@@QEAAPEBVCCharFormat@@J@Z; CTxtArray::GetCharFormat(long)
0x18005c9f6  or      edx, 0FFFFFFFFh; int
0x18005c9f9  mov     [rsp+450h+var_3F8], rax
0x18005c9fe  mov     ecx, ebx; int
0x18005ca00  call    ?ReleaseFormats@@YAXJJ@Z; ReleaseFormats(long,long)
0x18005ca05  mov     rbx, [rsp+450h+var_3F8]
0x18005ca0a  test    dword ptr [rdi+0B0h], 100000h
0x18005ca14  jz      short loc_18005CA95
0x18005ca16  test    dword ptr [rdi+0B4h], 80000h
0x18005ca20  xorps   xmm0, xmm0
0x18005ca23  movdqu  [rbp+350h+var_3D0], xmm0
0x18005ca28  mov     [rsp+450h+var_3D8], 0
0x18005ca31  mov     qword ptr [rbp+350h+var_3B8], 0
0x18005ca39  mov     [rbp+350h+var_3C0], r14
0x18005ca3d  jz      short loc_18005CA4E
0x18005ca3f  mov     edx, esi; int
0x18005ca41  mov     rcx, rdi; this
0x18005ca44  call    ?GetAcpFromCp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetAcpFromCp(long,int)
0x18005ca49  mov     [rbp+350h+var_3B8], eax
0x18005ca4c  jmp     short loc_18005CA51
0x18005ca4e  mov     [rbp+350h+var_3B8], esi
0x18005ca51  movzx   eax, byte ptr [rbx]
0x18005ca54  lea     r8, [rsp+450h+var_3D8]; void *
0x18005ca59  shr     eax, 4
0x18005ca5c  mov     edx, 703h; unsigned int
0x18005ca61  and     eax, 1
0x18005ca64  mov     rcx, rdi; this
0x18005ca67  mov     [rbp+350h+var_3B8+4], eax
0x18005ca6a  call    ?TxNotify@CTxtEdit@@QEAAJKPEAX@Z; CTxtEdit::TxNotify(ulong,void *)
0x18005ca6f  test    eax, eax
0x18005ca71  jnz     loc_18005CB1D
0x18005ca77  test    dword ptr [rdi+0B4h], 80000h
0x18005ca81  jz      short loc_18005CA92
0x18005ca83  mov     edx, [rbp+350h+var_3B8]; int
0x18005ca86  mov     rcx, rdi; this
0x18005ca89  call    ?GetCpFromAcp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetCpFromAcp(long,int)
0x18005ca8e  mov     esi, eax
0x18005ca90  jmp     short loc_18005CA95
0x18005ca92  mov     esi, [rbp+350h+var_3B8]
0x18005ca95  mov     edx, esi; int
0x18005ca97  mov     rcx, r13; this
0x18005ca9a  call    ?SetCp@CTxtRange@@QEAAJJ@Z; CTxtRange::SetCp(long)
0x18005ca9f  mov     rsi, [rsp+450h+var_3F0]
0x18005caa4  xor     ebx, ebx
0x18005caa6  test    r12d, r12d
0x18005caa9  jz      short loc_18005CB1D
0x18005caab  mov     r13, [rsp+450h+var_3E8]
0x18005cab0  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18005cab7  mov     r9d, 104h
0x18005cabd  mov     edx, ebx
0x18005cabf  mov     rcx, r14
0x18005cac2  jnz     short loc_18005CAF8
0x18005cac4  lea     r8, [rbp+350h+MultiByteStr]
0x18005cac8  mov     rax, r13
0x18005cacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cad0  lea     rax, [rbp+350h+WideCharStr]
0x18005cad7  mov     [rsp+450h+cchWideChar], 104h; cchWideChar
0x18005cadf  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18005cae3  mov     [rsp+450h+lpWideCharStr], rax; lpWideCharStr
0x18005cae8  lea     r8, [rbp+350h+MultiByteStr]; lpMultiByteStr
0x18005caec  xor     edx, edx; dwFlags
0x18005caee  xor     ecx, ecx; CodePage
0x18005caf0  call    cs:__imp_MultiByteToWideChar
0x18005caf6  jmp     short loc_18005CB07
0x18005caf8  lea     r8, [rbp+350h+WideCharStr]
0x18005caff  mov     rax, rsi
0x18005cb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb07  lea     rdx, [rbp+350h+WideCharStr]; unsigned __int16 *
0x18005cb0e  mov     rcx, rdi; this
0x18005cb11  call    ?InsertFromFile@CTxtEdit@@AEAA_JPEBG@Z; CTxtEdit::InsertFromFile(ushort const *)
0x18005cb16  inc     ebx
0x18005cb18  cmp     ebx, r12d
0x18005cb1b  jb      short loc_18005CAB0
0x18005cb1d  mov     rax, [rsp+450h+var_3E0]
0x18005cb22  mov     rcx, r14
0x18005cb25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb2a  mov     rcx, r15; hLibModule
0x18005cb2d  call    cs:__imp_FreeLibrary
0x18005cb33  xor     eax, eax
0x18005cb35  mov     rcx, [rbp+350h+var_40]
0x18005cb3c  xor     rcx, rsp; StackCookie
0x18005cb3f  call    __security_check_cookie
0x18005cb44  mov     rbx, [rsp+450h+arg_10]
0x18005cb4c  add     rsp, 420h
0x18005cb53  pop     r15
0x18005cb55  pop     r14
0x18005cb57  pop     r13
0x18005cb59  pop     r12
0x18005cb5b  pop     rdi
0x18005cb5c  pop     rsi
0x18005cb5d  pop     rbp
0x18005cb5e  retn
```
