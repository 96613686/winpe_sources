# CRecentFileList::UpdateMenu(CCmdUI *)

- ea: `0x180072120`
- end: `0x1800723ef`
- name: `?UpdateMenu@CRecentFileList@@UEAAXPEAVCCmdUI@@@Z`
- size: `719`
- prototype: `void __fastcall(CRecentFileList *__hidden this, struct CCmdUI *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x18000c0a0`
- `0x18000c860`
- `0x18000c950`
- `0x18000d5d0`
- `0x180019290`
- `0x1800347b8`
- `0x180071e80`
- `0x180072020`
- `0x180072120`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180072339`
- `msvcrt!swprintf_s` at `0x180072339`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180072214`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180072214`
- `USER32!GetMenuItemCount` at `0x1800723bf`
- `USER32!GetMenuItemCount` at `0x1800723bf`
- `USER32!DeleteMenu` at `0x1800721fc`
- `USER32!DeleteMenu` at `0x1800721fc`
- `USER32!InsertMenuW` at `0x18007238d`
- `USER32!InsertMenuW` at `0x18007238d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CRecentFileList::UpdateMenu(CRecentFileList *this, struct CCmdUI *a2)
{
  struct CString *v4; // rbx
  CMenu **v5; // rsi
  int i; // ebx
  __int64 v7; // rcx
  unsigned __int64 v8; // rdx
  int v9; // r12d
  int j; // r15d
  _WORD *v11; // rbx
  unsigned __int16 *v12; // rcx
  __int16 k; // ax
  unsigned __int16 v14; // ax
  CMenu *v15; // rbx
  CString *v16; // rax
  const WCHAR *lpNewItem; // r10
  unsigned int v18; // r8d
  UINT v19; // edx
  LPCWSTR v20; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR v21; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v22[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[8]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v24[16]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  v4 = (CRecentFileList *)((char *)this + 48);
  v5 = (CMenu **)((char *)a2 + 16);
  if ( !*(_DWORD *)(*((_QWORD *)this + 6) - 8LL) && *v5 )
    CMenu::GetMenuStringW(*v5, *((_DWORD *)a2 + 2), v4, 0);
  if ( *(_DWORD *)(**((_QWORD **)this + 2) - 8LL) )
  {
    if ( *v5 )
    {
      for ( i = 0; i < *((_DWORD *)this + 2); ++i )
        DeleteMenu(*((HMENU *)*v5 + 1), i + *((_DWORD *)a2 + 2), 0);
      if ( GetCurrentDirectoryW(0x104u, Buffer) - 1 <= 0x102 )
      {
        v7 = -1;
        do
          ++v7;
        while ( Buffer[v7] );
        if ( (unsigned int)v7 <= 0x102 )
        {
          Buffer[(int)v7] = 92;
          v8 = 2LL * (int)v7 + 2;
          if ( v8 >= 0x208 )
            _report_rangecheckfailure();
          v9 = v7 + 1;
          *(WCHAR *)((char *)Buffer + v8) = 0;
          v21 = _afxPchNil;
          v20 = _afxPchNil;
          for ( j = 0; j < *((_DWORD *)this + 2); ++j )
          {
            if ( !CRecentFileList::GetDisplayName(this, (struct CString *)&v21, j, Buffer, v9, 1) )
              break;
            v11 = v21;
            v12 = CString::GetBuffer((CString *)&v20, 2 * *((_DWORD *)v21 - 2));
            for ( k = *v11; *v11; k = *v11 )
            {
              if ( k == 38 )
                *v12++ = 38;
              v14 = *v11++;
              *v12++ = v14;
            }
            *v12 = 0;
            CString::ReleaseBuffer((CString *)&v20, -1);
            swprintf_s(v24, 0xAu, L"&%d ", (j + *((_DWORD *)this + 10) + 1) % 0xAu);
            v15 = *v5;
            v16 = CString::CString((CString *)v23, v24);
            lpNewItem = *(const WCHAR **)operator+(v22, v16, &v20);
            v18 = *((_DWORD *)a2 + 2);
            *((_DWORD *)a2 + 2) = v18 + 1;
            v19 = *((_DWORD *)a2 + 3);
            *((_DWORD *)a2 + 3) = v19 + 1;
            InsertMenuW(*((HMENU *)v15 + 1), v19, 0x400u, v18, lpNewItem);
            CString::~CString((CString *)v22);
            CString::~CString((CString *)v23);
          }
          --*((_DWORD *)a2 + 3);
          *((_DWORD *)a2 + 12) = GetMenuItemCount(*((HMENU *)*v5 + 1));
          *((_DWORD *)a2 + 10) = 1;
          CString::~CString((CString *)&v20);
          CString::~CString((CString *)&v21);
        }
      }
    }
  }
  else
  {
    if ( *(_DWORD *)(*(_QWORD *)v4 - 8LL) )
      (*(void (__fastcall **)(struct CCmdUI *))(*(_QWORD *)a2 + 24LL))(a2);
    (**(void (__fastcall ***)(struct CCmdUI *, _QWORD))a2)(a2, 0);
  }
}

```

## disassembly

```asm
0x180072120  mov     [rsp-8+arg_10], rbx
0x180072125  push    rbp
0x180072126  push    rsi
0x180072127  push    rdi
0x180072128  push    r12
0x18007212a  push    r13
0x18007212c  push    r14
0x18007212e  push    r15
0x180072130  lea     rbp, [rsp-190h]
0x180072138  sub     rsp, 290h
0x18007213f  mov     rax, cs:__security_cookie
0x180072146  xor     rax, rsp
0x180072149  mov     [rbp+1C0h+var_40], rax
0x180072150  mov     rdi, rdx
0x180072153  mov     r14, rcx
0x180072156  lea     rbx, [rcx+30h]
0x18007215a  mov     rax, [rbx]
0x18007215d  xor     r13d, r13d
0x180072160  lea     rsi, [rdx+10h]
0x180072164  cmp     [rax-8], r13d
0x180072168  jnz     short loc_180072180
0x18007216a  mov     rcx, [rsi]; this
0x18007216d  test    rcx, rcx
0x180072170  jz      short loc_180072180
0x180072172  xor     r9d, r9d; unsigned int
0x180072175  mov     r8, rbx; struct CString *
0x180072178  mov     edx, [rdx+8]; unsigned int
0x18007217b  call    ?GetMenuStringW@CMenu@@QEBAHIAEAVCString@@I@Z; CMenu::GetMenuStringW(uint,CString &,uint)
0x180072180  mov     rax, [r14+10h]
0x180072184  mov     rcx, [rax]
0x180072187  cmp     [rcx-8], r13d
0x18007218b  jnz     short loc_1800721DF
0x18007218d  mov     rdx, [rbx]
0x180072190  cmp     [rdx-8], r13d
0x180072194  jz      short loc_1800721A5
0x180072196  mov     rax, [rdi]
0x180072199  mov     rcx, rdi
0x18007219c  mov     rax, [rax+18h]
0x1800721a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721a5  mov     rax, [rdi]
0x1800721a8  xor     edx, edx
0x1800721aa  mov     rcx, rdi
0x1800721ad  mov     rax, [rax]
0x1800721b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721b5  mov     rcx, [rbp+1C0h+var_40]
0x1800721bc  xor     rcx, rsp; StackCookie
0x1800721bf  call    __security_check_cookie
0x1800721c4  mov     rbx, [rsp+2C0h+arg_10]
0x1800721cc  add     rsp, 290h
0x1800721d3  pop     r15
0x1800721d5  pop     r14
0x1800721d7  pop     r13
0x1800721d9  pop     r12
0x1800721db  pop     rdi
0x1800721dc  pop     rsi
0x1800721dd  pop     rbp
0x1800721de  retn
0x1800721df  cmp     [rsi], r13
0x1800721e2  jz      short loc_1800721B5
0x1800721e4  mov     ebx, r13d
0x1800721e7  cmp     [r14+8], r13d
0x1800721eb  jle     short loc_18007220A
0x1800721ed  mov     edx, [rdi+8]
0x1800721f0  add     edx, ebx; uPosition
0x1800721f2  mov     rcx, [rsi]
0x1800721f5  xor     r8d, r8d; uFlags
0x1800721f8  mov     rcx, [rcx+8]; hMenu
0x1800721fc  call    cs:__imp_DeleteMenu
0x180072202  inc     ebx
0x180072204  cmp     ebx, [r14+8]
0x180072208  jl      short loc_1800721ED
0x18007220a  lea     rdx, [rsp+2C0h+Buffer]; lpBuffer
0x18007220f  mov     ecx, 104h; nBufferLength
0x180072214  call    cs:__imp_GetCurrentDirectoryW
0x18007221a  dec     eax
0x18007221c  mov     edx, 102h
0x180072221  cmp     eax, edx
0x180072223  ja      short loc_1800721B5
0x180072225  lea     rax, [rsp+2C0h+Buffer]
0x18007222a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007222e  inc     rcx
0x180072231  cmp     [rax+rcx*2], r13w
0x180072236  jnz     short loc_18007222E
0x180072238  cmp     ecx, edx
0x18007223a  ja      loc_1800721B5
0x180072240  movsxd  rax, ecx
0x180072243  mov     edx, 5Ch ; '\'
0x180072248  mov     [rsp+rax*2+2C0h+Buffer], dx
0x18007224d  lea     rdx, ds:2[rax*2]
0x180072255  cmp     rdx, 208h
0x18007225c  jnb     loc_1800723E9
0x180072262  lea     r12d, [rcx+1]
0x180072266  mov     [rsp+rdx+2C0h+Buffer], r13w
0x18007226c  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x180072273  mov     [rsp+2C0h+var_288], rax
0x180072278  mov     [rsp+2C0h+var_290], rax
0x18007227d  mov     r15d, r13d
0x180072280  cmp     [r14+8], r13d
0x180072284  jle     loc_1800723B5
0x18007228a  mov     [rsp+2C0h+var_298], 1; int
0x180072292  mov     dword ptr [rsp+2C0h+lpNewItem], r12d; int
0x180072297  lea     r9, [rsp+2C0h+Buffer]; unsigned __int16 *
0x18007229c  mov     r8d, r15d; int
0x18007229f  lea     rdx, [rsp+2C0h+var_288]; struct CString *
0x1800722a4  mov     rcx, r14; this
0x1800722a7  call    ?GetDisplayName@CRecentFileList@@QEBAHAEAVCString@@HPEBGHH@Z; CRecentFileList::GetDisplayName(CString &,int,ushort const *,int,int)
0x1800722ac  test    eax, eax
0x1800722ae  jz      loc_1800723B5
0x1800722b4  mov     rbx, [rsp+2C0h+var_288]
0x1800722b9  mov     edx, [rbx-8]
0x1800722bc  add     edx, edx; int
0x1800722be  lea     rcx, [rsp+2C0h+var_290]; this
0x1800722c3  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x1800722c8  mov     rcx, rax
0x1800722cb  movzx   eax, word ptr [rbx]
0x1800722ce  test    ax, ax
0x1800722d1  jz      short loc_1800722FA
0x1800722d3  mov     edx, 26h ; '&'
0x1800722d8  cmp     ax, dx
0x1800722db  jnz     short loc_1800722E4
0x1800722dd  mov     [rcx], dx
0x1800722e0  add     rcx, 2
0x1800722e4  movzx   eax, word ptr [rbx]
0x1800722e7  add     rbx, 2
0x1800722eb  mov     [rcx], ax
0x1800722ee  add     rcx, 2
0x1800722f2  movzx   eax, word ptr [rbx]
0x1800722f5  test    ax, ax
0x1800722f8  jnz     short loc_1800722D8
0x1800722fa  mov     [rcx], r13w
0x1800722fe  or      edx, 0FFFFFFFFh; int
0x180072301  lea     rcx, [rsp+2C0h+var_290]; this
0x180072306  call    ?ReleaseBuffer@CString@@QEAAXH@Z; CString::ReleaseBuffer(int)
0x18007230b  mov     r9d, [r14+28h]
0x18007230f  inc     r9d
0x180072312  add     r9d, r15d
0x180072315  mov     eax, 0CCCCCCCDh
0x18007231a  mul     r9d
0x18007231d  shr     edx, 3
0x180072320  lea     eax, [rdx+rdx*4]
0x180072323  add     eax, eax
0x180072325  sub     r9d, eax
0x180072328  lea     r8, aD_2; "&%d "
0x18007232f  mov     edx, 0Ah; BufferCount
0x180072334  lea     rcx, [rsp+2C0h+var_270]; Buffer
0x180072339  call    cs:__imp_swprintf_s
0x18007233f  mov     rbx, [rsi]
0x180072342  lea     rdx, [rsp+2C0h+var_270]; unsigned __int16 *
0x180072347  lea     rcx, [rsp+2C0h+var_278]; this
0x18007234c  call    ??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x180072351  nop
0x180072352  lea     r8, [rsp+2C0h+var_290]
0x180072357  mov     rdx, rax
0x18007235a  lea     rcx, [rsp+2C0h+var_280]
0x18007235f  call    ??H@YA?AVCString@@AEBV0@0@Z; operator+(CString const &,CString const &)
0x180072364  mov     r10, [rax]
0x180072367  mov     r8d, [rdi+8]
0x18007236b  lea     eax, [r8+1]
0x18007236f  mov     [rdi+8], eax
0x180072372  mov     edx, [rdi+0Ch]; uPosition
0x180072375  lea     eax, [rdx+1]
0x180072378  mov     [rdi+0Ch], eax
0x18007237b  mov     r9d, r8d; uIDNewItem
0x18007237e  mov     [rsp+2C0h+lpNewItem], r10; lpNewItem
0x180072383  mov     r8d, 400h; uFlags
0x180072389  mov     rcx, [rbx+8]; hMenu
0x18007238d  call    cs:__imp_InsertMenuW
0x180072393  lea     rcx, [rsp+2C0h+var_280]; this
0x180072398  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18007239d  nop
0x18007239e  lea     rcx, [rsp+2C0h+var_278]; this
0x1800723a3  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800723a8  inc     r15d
0x1800723ab  cmp     r15d, [r14+8]
0x1800723af  jl      loc_18007228A
0x1800723b5  dec     dword ptr [rdi+0Ch]
0x1800723b8  mov     rcx, [rsi]
0x1800723bb  mov     rcx, [rcx+8]; hMenu
0x1800723bf  call    cs:__imp_GetMenuItemCount
0x1800723c5  mov     [rdi+30h], eax
0x1800723c8  mov     dword ptr [rdi+28h], 1
0x1800723cf  lea     rcx, [rsp+2C0h+var_290]; this
0x1800723d4  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800723d9  nop
0x1800723da  lea     rcx, [rsp+2C0h+var_288]; this
0x1800723df  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800723e4  jmp     loc_1800721B5
0x1800723e9  call    __report_rangecheckfailure
```
