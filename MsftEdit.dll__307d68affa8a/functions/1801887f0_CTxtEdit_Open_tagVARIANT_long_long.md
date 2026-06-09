# CTxtEdit::Open(tagVARIANT *,long,long)

- ea: `0x1801887f0`
- end: `0x180188b3a`
- name: `?Open@CTxtEdit@@UEAAJPEAUtagVARIANT@@JJ@Z`
- size: `842`
- prototype: `int(CTxtEdit *__hidden this, struct tagVARIANT *, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180021c38`
- `0x180067f60`
- `0x18010214c`
- `0x1801376bc`
- `0x1801880f8`
- `0x1801887f0`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018897c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018897c`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x180188852`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x180188852`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018898e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180188ae3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18018898e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180188ae3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180188a4b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180188a4b`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180188944`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180188944`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180188931`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180188931`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x180188a65`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x180188a65`

## pseudocode

```c
__int64 __fastcall CTxtEdit::Open(CTxtEdit *this, struct tagVARIANT *a2, int a3, UINT a4)
{
  DWORD v8; // r13d
  __int64 result; // rax
  int v10; // edi
  struct CDocInfo *DocInfo; // rax
  struct CDocInfo *v12; // r15
  int v13; // edx
  DWORD dwCreationDisposition; // ebx
  HANDLE FileW; // rax
  unsigned __int16 *v16; // rax
  DWORD_PTR dwCookie; // rax
  signed int LastError; // ebx
  __int64 (__fastcall ***llVal)(_QWORD, GUID *, DWORD_PTR *); // rcx
  LONG StreamFlags; // eax
  signed int v21; // r12d
  HCURSOR CursorW; // rax
  int v23; // r8d
  HICON v24; // rbx
  int v25; // r8d
  DWORD_PTR v26; // [rsp+40h] [rbp-29h] BYREF
  __int64 v27; // [rsp+48h] [rbp-21h] BYREF
  struct _editstream hObject; // [rsp+50h] [rbp-19h] BYREF
  struct _editstream v29; // [rsp+70h] [rbp+7h] BYREF
  DWORD dwShareMode; // [rsp+D8h] [rbp+6Fh]
  DWORD dwDesiredAccess; // [rsp+E0h] [rbp+77h] BYREF

  hObject.dwCookie = 0;
  hObject.dwError = 0;
  hObject.pfnCallback = (EDITSTREAMCALLBACK)MyRead;
  v26 = 0;
  v27 = 0;
  if ( !a2 || a4 && (a4 & 0xFFFFFFFE) != 0x4B0 && !IsValidCodePage(a4) )
    return 2147942487LL;
  v8 = a3 & 0xF;
  if ( v8 >= 3 )
    return 2147500033LL;
  v10 = a3 & 0x1000;
  if ( (a3 & 0x1000) == 0 )
    (*(void (__fastcall **)(CTxtEdit *))(*(_QWORD *)this + 120LL))(this);
  DocInfo = CTxtEdit::GetDocInfo((CTxtEdit *)((char *)this - 16));
  v12 = DocInfo;
  if ( !DocInfo )
    return 2147942414LL;
  *((_WORD *)DocInfo + 56) = a3 & 0xFF0F;
  dwDesiredAccess = ~(a3 << 22) & 0x40000000 | 0x80000000;
  v13 = (a3 & 0x200) == 0;
  if ( (a3 & 0x400) == 0 )
    v13 = ((a3 & 0x200) == 0) | 2;
  dwCreationDisposition = (a3 >> 4) & 0xF;
  dwShareMode = v13;
  if ( !dwCreationDisposition )
    dwCreationDisposition = 4;
  if ( a2->vt != 8 || !CW32System::SysStringLen(a2->bstrVal) )
  {
    if ( a2->vt != 13 )
    {
LABEL_32:
      dwDesiredAccess = v8;
      v29 = hObject;
      StreamFlags = GetStreamFlags(&v29, (int *)&dwDesiredAccess, a4);
      if ( a2->vt == 13 && v26 )
        (*(void (__fastcall **)(DWORD_PTR, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v26 + 40LL))(v26, StreamFlags, 0, 0);
      else
        SetFilePointer((HANDLE)hObject.dwCookie, StreamFlags, 0, 0);
      v21 = dwDesiredAccess;
      if ( v10 )
        v21 = dwDesiredAccess | 0x8000;
      CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
      v24 = CTxtEdit::TxSetCursor((CTxtEdit *)((char *)this - 16), CursorW, v23);
      (*(void (__fastcall **)(char *, __int64, __int64, struct _editstream *, __int64 *))(*((_QWORD *)this - 2) + 24LL))(
        (char *)this - 16,
        1097,
        v21 | 0x1000LL,
        &hObject,
        &v27);
      CTxtEdit::TxSetCursor((CTxtEdit *)((char *)this - 16), v24, v25);
      if ( v26 )
      {
        (*(void (__fastcall **)(DWORD_PTR))(*(_QWORD *)v26 + 16LL))(v26);
      }
      else if ( dwShareMode == 3 || v10 )
      {
        if ( a2->vt != 13 && hObject.dwCookie )
          CloseHandle((HANDLE)hObject.dwCookie);
        if ( !v10 )
          *((_QWORD *)v12 + 3) = 0;
      }
      *((_DWORD *)this + 40) &= ~0x4000000u;
      *((_DWORD *)this + 40) |= v10 == 0 ? 0x4000000 : 0;
      return hObject.dwError;
    }
    llVal = (__int64 (__fastcall ***)(_QWORD, GUID *, DWORD_PTR *))a2->llVal;
    if ( llVal )
    {
      result = (**llVal)(llVal, &IID_IStream, &v26);
      if ( (_DWORD)result )
        return result;
      hObject.dwCookie = v26;
      hObject.pfnCallback = (EDITSTREAMCALLBACK)MyStreamRead;
      goto LABEL_32;
    }
    return 2147942487LL;
  }
  FileW = CreateFileW(a2->bstrVal, dwDesiredAccess, dwShareMode, 0, dwCreationDisposition, 0x110000u, 0);
  hObject.dwCookie = (DWORD_PTR)FileW;
  if ( FileW != (HANDLE)-1LL && GetFileType(FileW) == 1 )
  {
    if ( v10 )
      goto LABEL_32;
    v16 = CW32System::SysAllocString(a2->bstrVal);
    *(_QWORD *)v12 = v16;
    if ( v16 )
    {
      dwCookie = hObject.dwCookie;
      *((_WORD *)v12 + 56) |= 0x50u;
      *((_QWORD *)v12 + 3) = dwCookie;
      goto LABEL_32;
    }
    return 2147942414LL;
  }
  LastError = GetLastError();
  if ( hObject.dwCookie != -1 )
    CloseHandle((HANDLE)hObject.dwCookie);
  if ( LastError )
  {
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1801887f0  mov     [rsp-8+arg_0], rbx
0x1801887f5  push    rbp
0x1801887f6  push    rsi
0x1801887f7  push    rdi
0x1801887f8  push    r12
0x1801887fa  push    r13
0x1801887fc  push    r14
0x1801887fe  push    r15
0x180188800  lea     rbp, [rsp-27h]
0x180188805  sub     rsp, 90h
0x18018880c  xor     edi, edi
0x18018880e  lea     rax, ?MyRead@@YAK_KPEAEJPEAJ@Z; MyRead(unsigned __int64,uchar *,long,long *)
0x180188815  mov     [rbp+57h+hObject], rdi
0x180188819  mov     r12d, r9d
0x18018881c  mov     dword ptr [rbp+57h+hObject+8], edi
0x18018881f  mov     ebx, r8d
0x180188822  mov     [rbp+57h+hObject+0Ch], rax
0x180188826  mov     r14, rdx
0x180188829  mov     [rbp+57h+var_80], rdi
0x18018882d  mov     rsi, rcx
0x180188830  mov     [rbp+57h+var_78], rdi
0x180188834  test    rdx, rdx
0x180188837  jz      loc_180188B1A
0x18018883d  test    r9d, r9d
0x180188840  jz      short loc_180188860
0x180188842  mov     eax, r9d
0x180188845  and     eax, 0FFFFFFFEh
0x180188848  cmp     eax, 4B0h
0x18018884d  jz      short loc_180188860
0x18018884f  mov     ecx, r9d; CodePage
0x180188852  call    cs:__imp_IsValidCodePage
0x180188858  test    eax, eax
0x18018885a  jz      loc_180188B1A
0x180188860  mov     r13d, ebx
0x180188863  and     r13d, 0Fh
0x180188867  cmp     r13d, 3
0x18018886b  jb      short loc_180188877
0x18018886d  mov     eax, 80004001h
0x180188872  jmp     loc_180188B1F
0x180188877  mov     edi, ebx
0x180188879  and     edi, 1000h
0x18018887f  jnz     short loc_180188890
0x180188881  mov     rax, [rsi]
0x180188884  mov     rcx, rsi
0x180188887  mov     rax, [rax+78h]
0x18018888b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188890  lea     rcx, [rsi-10h]; this
0x180188894  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x180188899  mov     r15, rax
0x18018889c  test    rax, rax
0x18018889f  jz      loc_180188B13
0x1801888a5  movzx   ecx, bx
0x1801888a8  mov     eax, 0FF0Fh
0x1801888ad  and     cx, ax
0x1801888b0  mov     eax, ebx
0x1801888b2  shl     eax, 16h
0x1801888b5  mov     [r15+70h], cx
0x1801888ba  not     eax
0x1801888bc  and     eax, 0C0000000h
0x1801888c1  mov     ecx, ebx
0x1801888c3  shr     ecx, 9
0x1801888c6  bts     eax, 1Fh
0x1801888ca  not     ecx
0x1801888cc  mov     [rbp+57h+dwDesiredAccess], eax
0x1801888cf  and     ecx, 1
0x1801888d2  mov     eax, 4
0x1801888d7  or      ecx, 2
0x1801888da  mov     edx, ecx
0x1801888dc  and     edx, 0FFFFFFFDh
0x1801888df  bt      ebx, 0Ah
0x1801888e3  cmovnb  edx, ecx
0x1801888e6  sar     ebx, 4
0x1801888e9  and     ebx, 0Fh
0x1801888ec  mov     [rbp+57h+dwShareMode], edx
0x1801888ef  cmovz   ebx, eax
0x1801888f2  cmp     word ptr [r14], 8
0x1801888f7  jnz     loc_1801889B1
0x1801888fd  mov     rcx, [r14+8]; unsigned __int16 *
0x180188901  call    ?SysStringLen@CW32System@@SAIPEAG@Z; CW32System::SysStringLen(ushort *)
0x180188906  test    eax, eax
0x180188908  jz      loc_1801889B1
0x18018890e  mov     r8d, [rbp+57h+dwShareMode]; dwShareMode
0x180188912  xor     r9d, r9d; lpSecurityAttributes
0x180188915  mov     edx, [rbp+57h+dwDesiredAccess]; dwDesiredAccess
0x180188918  mov     rcx, [r14+8]; lpFileName
0x18018891c  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x180188925  mov     [rsp+0C0h+dwFlagsAndAttributes], 110000h; dwFlagsAndAttributes
0x18018892d  mov     [rsp+0C0h+dwCreationDisposition], ebx; dwCreationDisposition
0x180188931  call    cs:__imp_CreateFileW
0x180188937  mov     [rbp+57h+hObject], rax
0x18018893b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18018893f  jz      short loc_18018897C
0x180188941  mov     rcx, rax; hFile
0x180188944  call    cs:__imp_GetFileType
0x18018894a  cmp     eax, 1
0x18018894d  jnz     short loc_18018897C
0x18018894f  test    edi, edi
0x180188951  jnz     loc_1801889F6
0x180188957  mov     rcx, [r14+8]; unsigned __int16 *
0x18018895b  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x180188960  mov     [r15], rax
0x180188963  test    rax, rax
0x180188966  jz      loc_180188B13
0x18018896c  mov     rax, [rbp+57h+hObject]
0x180188970  or      word ptr [r15+70h], 50h
0x180188976  mov     [r15+18h], rax
0x18018897a  jmp     short loc_1801889F6
0x18018897c  call    cs:__imp_GetLastError
0x180188982  mov     rcx, [rbp+57h+hObject]; hObject
0x180188986  mov     ebx, eax
0x180188988  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18018898c  jz      short loc_180188994
0x18018898e  call    cs:__imp_CloseHandle
0x180188994  test    ebx, ebx
0x180188996  jnz     short loc_18018899F
0x180188998  mov     ebx, 80070057h
0x18018899d  jmp     short loc_1801889AA
0x18018899f  jle     short loc_1801889AA
0x1801889a1  movzx   ebx, bx
0x1801889a4  or      ebx, 80070000h
0x1801889aa  mov     eax, ebx
0x1801889ac  jmp     loc_180188B1F
0x1801889b1  cmp     word ptr [r14], 0Dh
0x1801889b6  jnz     short loc_1801889F6
0x1801889b8  mov     rcx, [r14+8]
0x1801889bc  test    rcx, rcx
0x1801889bf  jz      loc_180188B1A
0x1801889c5  mov     rax, [rcx]
0x1801889c8  lea     r8, [rbp+57h+var_80]
0x1801889cc  lea     rdx, IID_IStream
0x1801889d3  mov     rax, [rax]
0x1801889d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801889db  test    eax, eax
0x1801889dd  jnz     loc_180188B1F
0x1801889e3  mov     rax, [rbp+57h+var_80]
0x1801889e7  mov     [rbp+57h+hObject], rax
0x1801889eb  lea     rax, ?MyStreamRead@@YAK_KPEAEJPEAJ@Z; MyStreamRead(unsigned __int64,uchar *,long,long *)
0x1801889f2  mov     [rbp+57h+hObject+0Ch], rax
0x1801889f6  movups  xmm0, xmmword ptr [rbp+57h+hObject]
0x1801889fa  mov     eax, [rbp+57h+var_60]
0x1801889fd  lea     rdx, [rbp+57h+dwDesiredAccess]; int *
0x180188a01  mov     r8d, r12d; int
0x180188a04  mov     [rbp+57h+dwDesiredAccess], r13d
0x180188a08  lea     rcx, [rbp+57h+var_50]; struct _editstream
0x180188a0c  movaps  xmmword ptr [rbp+57h+var_50.dwCookie], xmm0
0x180188a10  mov     dword ptr [rbp+57h+var_50.pfnCallback+4], eax
0x180188a13  call    ?GetStreamFlags@@YAJU_editstream@@AEAJJ@Z; GetStreamFlags(_editstream,long &,long)
0x180188a18  cmp     word ptr [r14], 0Dh
0x180188a1d  jnz     short loc_180188A3F
0x180188a1f  mov     rcx, [rbp+57h+var_80]
0x180188a23  test    rcx, rcx
0x180188a26  jz      short loc_180188A3F
0x180188a28  movsxd  rdx, eax
0x180188a2b  xor     r9d, r9d
0x180188a2e  mov     rax, [rcx]
0x180188a31  xor     r8d, r8d
0x180188a34  mov     rax, [rax+28h]
0x180188a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188a3d  jmp     short loc_180188A51
0x180188a3f  mov     rcx, [rbp+57h+hObject]; hFile
0x180188a43  xor     r9d, r9d; dwMoveMethod
0x180188a46  xor     r8d, r8d; lpDistanceToMoveHigh
0x180188a49  mov     edx, eax; lDistanceToMove
0x180188a4b  call    cs:__imp_SetFilePointer
0x180188a51  mov     r12d, [rbp+57h+dwDesiredAccess]
0x180188a55  test    edi, edi
0x180188a57  jz      short loc_180188A5E
0x180188a59  bts     r12d, 0Fh
0x180188a5e  mov     edx, 7F02h; lpCursorName
0x180188a63  xor     ecx, ecx; hInstance
0x180188a65  call    cs:__imp_LoadCursorW
0x180188a6b  lea     r13, [rsi-10h]
0x180188a6f  mov     rdx, rax; HICON
0x180188a72  mov     rcx, r13; this
0x180188a75  call    ?TxSetCursor@CTxtEdit@@QEAAPEAUHICON__@@PEAU2@H@Z; CTxtEdit::TxSetCursor(HICON__ *,int)
0x180188a7a  mov     rdx, [rsi-10h]
0x180188a7e  lea     rcx, [rbp+57h+var_78]
0x180188a82  mov     rbx, rax
0x180188a85  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx
0x180188a8a  movsxd  r8, r12d
0x180188a8d  lea     r9, [rbp+57h+hObject]
0x180188a91  bts     r8, 0Ch
0x180188a96  mov     rcx, r13
0x180188a99  mov     rax, [rdx+18h]
0x180188a9d  mov     edx, 449h
0x180188aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188aa7  mov     rdx, rbx; HICON
0x180188aaa  mov     rcx, r13; this
0x180188aad  call    ?TxSetCursor@CTxtEdit@@QEAAPEAUHICON__@@PEAU2@H@Z; CTxtEdit::TxSetCursor(HICON__ *,int)
0x180188ab2  mov     rcx, [rbp+57h+var_80]
0x180188ab6  test    rcx, rcx
0x180188ab9  jz      short loc_180188AC9
0x180188abb  mov     rax, [rcx]
0x180188abe  mov     rax, [rax+10h]
0x180188ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188ac7  jmp     short loc_180188AF5
0x180188ac9  cmp     [rbp+57h+dwShareMode], 3
0x180188acd  jz      short loc_180188AD3
0x180188acf  test    edi, edi
0x180188ad1  jz      short loc_180188AF5
0x180188ad3  cmp     word ptr [r14], 0Dh
0x180188ad8  jz      short loc_180188AE9
0x180188ada  mov     rcx, [rbp+57h+hObject]; hObject
0x180188ade  test    rcx, rcx
0x180188ae1  jz      short loc_180188AE9
0x180188ae3  call    cs:__imp_CloseHandle
0x180188ae9  test    edi, edi
0x180188aeb  jnz     short loc_180188AF5
0x180188aed  mov     qword ptr [r15+18h], 0
0x180188af5  btr     dword ptr [rsi+0A0h], 1Ah
0x180188afd  neg     edi
0x180188aff  sbb     eax, eax
0x180188b01  not     eax
0x180188b03  and     eax, 4000000h
0x180188b08  or      [rsi+0A0h], eax
0x180188b0e  mov     eax, dword ptr [rbp+57h+hObject+8]
0x180188b11  jmp     short loc_180188B1F
0x180188b13  mov     eax, 8007000Eh
0x180188b18  jmp     short loc_180188B1F
0x180188b1a  mov     eax, 80070057h
0x180188b1f  mov     rbx, [rsp+0C0h+arg_0]
0x180188b27  add     rsp, 90h
0x180188b2e  pop     r15
0x180188b30  pop     r14
0x180188b32  pop     r13
0x180188b34  pop     r12
0x180188b36  pop     rdi
0x180188b37  pop     rsi
0x180188b38  pop     rbp
0x180188b39  retn
```
