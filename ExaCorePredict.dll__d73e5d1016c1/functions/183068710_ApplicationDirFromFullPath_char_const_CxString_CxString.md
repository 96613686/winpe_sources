# ApplicationDirFromFullPath(char const *,CxString &,CxString &)

- ea: `0x183068710`
- end: `0x183068918`
- name: `?ApplicationDirFromFullPath@@YA_NPEBDAEAVCxString@@1@Z`
- size: `520`
- prototype: `bool __fastcall(const char *FullPath, struct CxString *this, struct CxString *)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x1815ce380`
- `0x182dcc6d0`
- `0x183051f90`
- `0x183052e40`
- `0x183053010`
- `0x183053170`
- `0x183054b40`
- `0x183055940`
- `0x183055970`
- `0x1830566f0`
- `0x183068710`
- `0x1832ce3b0`
- `0x1832cefe4`

## import_xrefs

- `api-ms-win-crt-filesystem-l1-1-0!_makepath_s` at `0x183068816`
- `api-ms-win-crt-filesystem-l1-1-0!_makepath_s` at `0x183068816`
- `api-ms-win-crt-filesystem-l1-1-0!_splitpath_s` at `0x1830687df`
- `api-ms-win-crt-filesystem-l1-1-0!_splitpath_s` at `0x1830687df`

## string_xrefs

- `0x183068784`: `INTERNAL ERROR: The startup executable path name (%s) is too long. This  may prevent the program from working properly.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall ApplicationDirFromFullPath(const char *FullPath, struct CxString *this, struct CxString *a3)
{
  __int64 v6; // rbx
  unsigned __int64 v7; // rax
  unsigned __int64 v9; // rbx
  const char *CharPointer; // rax
  _BYTE v11[8]; // [rsp+50h] [rbp-458h] BYREF
  __int64 v12; // [rsp+58h] [rbp-450h]
  char Drive[16]; // [rsp+60h] [rbp-448h] BYREF
  char Ext[256]; // [rsp+70h] [rbp-438h] BYREF
  char Buffer[272]; // [rsp+170h] [rbp-338h] BYREF
  char Filename[256]; // [rsp+280h] [rbp-228h] BYREF
  char Dir[256]; // [rsp+380h] [rbp-128h] BYREF

  v12 = -2;
  CxString::Resize(this, 0, 95);
  if ( FullPath && *FullPath )
  {
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( FullPath[v7] );
    if ( v7 > 0x104 )
    {
      CxReportError(
        "INTERNAL ERROR: The startup executable path name (%s) is too long. This  may prevent the program from working properly.",
        FullPath);
      return 0;
    }
    _splitpath_s(FullPath, Drive, 3u, Dir, 0x100u, Filename, 0x100u, Ext, 0x100u);
    _makepath_s(Buffer, 0x104u, Drive, Dir, Filename, Ext);
    do
      ++v6;
    while ( Buffer[v6] );
    if ( Ext[v6 + 255] == 92 )
    {
      v9 = v6 - 1;
      if ( v9 >= 0x104 )
        _report_rangecheckfailure();
      Buffer[v9] = 0;
    }
    CxString::CxString((CxString *)v11, Buffer);
    CxString::operator=(this, v11);
    CxString::~CxString((CxString *)v11);
    CxString::CxString((CxString *)v11, Filename);
    CxString::operator=(a3, v11);
    CxString::~CxString((CxString *)v11);
    if ( !Ext[0] )
      CxStrNCpy(Ext, 0x100u, ".exe");
    CxString::operator+=(a3, Ext);
  }
  if ( CxString::IsEmpty(this) )
    return 0;
  CharPointer = CxString::GetCharPointer(this);
  SetStartupDir(CharPointer);
  return 1;
}

```

## disassembly

```asm
0x183068710  push    rbp
0x183068712  push    rsi
0x183068713  push    rdi
0x183068714  sub     rsp, 490h
0x18306871b  mov     [rsp+4A8h+var_450], 0FFFFFFFFFFFFFFFEh
0x183068724  mov     [rsp+4A8h+arg_18], rbx
0x18306872c  mov     rax, cs:__security_cookie
0x183068733  xor     rax, rsp
0x183068736  mov     [rsp+4A8h+var_28], rax
0x18306873e  mov     rbp, r8
0x183068741  mov     rsi, rdx
0x183068744  mov     rdi, rcx
0x183068747  mov     r8b, 5Fh ; '_'; char
0x18306874a  xor     edx, edx; unsigned __int64
0x18306874c  mov     rcx, rsi; this
0x18306874f  call    ?Resize@CxString@@QEAAX_KD@Z; CxString::Resize(unsigned __int64,char)
0x183068754  test    rdi, rdi
0x183068757  jz      loc_1830688D3
0x18306875d  cmp     byte ptr [rdi], 0
0x183068760  jz      loc_1830688D3
0x183068766  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18306876a  mov     rax, rbx
0x18306876d  nop     dword ptr [rax]
0x183068770  inc     rax
0x183068773  cmp     byte ptr [rdi+rax], 0
0x183068777  jnz     short loc_183068770
0x183068779  cmp     rax, 104h
0x18306877f  jbe     short loc_183068797
0x183068781  mov     rdx, rdi
0x183068784  lea     rcx, aInternalErrorT_0; "INTERNAL ERROR: The startup executable "...
0x18306878b  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x183068790  xor     al, al
0x183068792  jmp     loc_1830688F5
0x183068797  mov     [rsp+4A8h+ExtCount], 100h; ExtCount
0x1830687a0  lea     rax, [rsp+4A8h+var_438]
0x1830687a5  mov     [rsp+4A8h+Ext], rax; Ext
0x1830687aa  mov     [rsp+4A8h+FilenameCount], 100h; FilenameCount
0x1830687b3  lea     rax, [rsp+4A8h+var_228]
0x1830687bb  mov     [rsp+4A8h+Filename], rax; Filename
0x1830687c0  mov     [rsp+4A8h+DirCount], 100h; DirCount
0x1830687c9  lea     r9, [rsp+4A8h+Dir]; Dir
0x1830687d1  mov     r8d, 3; DriveCount
0x1830687d7  lea     rdx, [rsp+4A8h+Drive]; Drive
0x1830687dc  mov     rcx, rdi; FullPath
0x1830687df  call    cs:__imp__splitpath_s
0x1830687e5  lea     rax, [rsp+4A8h+var_438]
0x1830687ea  mov     [rsp+4A8h+Filename], rax; Ext
0x1830687ef  lea     rax, [rsp+4A8h+var_228]
0x1830687f7  mov     [rsp+4A8h+DirCount], rax; Filename
0x1830687fc  lea     r9, [rsp+4A8h+Dir]; Dir
0x183068804  lea     r8, [rsp+4A8h+Drive]; Drive
0x183068809  mov     edx, 104h; BufferCount
0x18306880e  lea     rcx, [rsp+4A8h+Buffer]; Buffer
0x183068816  call    cs:__imp__makepath_s
0x18306881c  lea     rax, [rsp+4A8h+Buffer]
0x183068824  inc     rbx
0x183068827  cmp     byte ptr [rax+rbx], 0
0x18306882b  jnz     short loc_183068824
0x18306882d  cmp     [rsp+rbx+4A8h+var_339], 5Ch ; '\'
0x183068835  jnz     short loc_183068853
0x183068837  dec     rbx
0x18306883a  cmp     rbx, 104h
0x183068841  jnb     short loc_18306884D
0x183068843  mov     [rsp+rbx+4A8h+Buffer], 0
0x18306884b  jmp     short loc_183068853
0x18306884d  call    __report_rangecheckfailure
0x183068853  lea     rdx, [rsp+4A8h+Buffer]; char *
0x18306885b  lea     rcx, [rsp+4A8h+var_458]; this
0x183068860  call    ??0CxString@@QEAA@PEBD@Z; CxString::CxString(char const *)
0x183068865  nop
0x183068866  lea     rdx, [rsp+4A8h+var_458]
0x18306886b  mov     rcx, rsi
0x18306886e  call    ??4CxString@@QEAAAEAV0@AEBV0@@Z; CxString::operator=(CxString const &)
0x183068873  nop
0x183068874  lea     rcx, [rsp+4A8h+var_458]; this
0x183068879  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x18306887e  lea     rdx, [rsp+4A8h+var_228]; char *
0x183068886  lea     rcx, [rsp+4A8h+var_458]; this
0x18306888b  call    ??0CxString@@QEAA@PEBD@Z; CxString::CxString(char const *)
0x183068890  nop
0x183068891  lea     rdx, [rsp+4A8h+var_458]
0x183068896  mov     rcx, rbp
0x183068899  call    ??4CxString@@QEAAAEAV0@AEBV0@@Z; CxString::operator=(CxString const &)
0x18306889e  nop
0x18306889f  lea     rcx, [rsp+4A8h+var_458]; this
0x1830688a4  call    ??1CxString@@QEAA@XZ; CxString::~CxString(void)
0x1830688a9  cmp     [rsp+4A8h+var_438], 0
0x1830688ae  jnz     short loc_1830688C6
0x1830688b0  lea     r8, aExe; ".exe"
0x1830688b7  mov     edx, 100h; unsigned __int64
0x1830688bc  lea     rcx, [rsp+4A8h+var_438]; char *
0x1830688c1  call    ?CxStrNCpy@@YAPEADPEAD_KPEBD@Z; CxStrNCpy(char *,unsigned __int64,char const *)
0x1830688c6  lea     rdx, [rsp+4A8h+var_438]
0x1830688cb  mov     rcx, rbp
0x1830688ce  call    ??YCxString@@QEAAAEAV0@PEBD@Z; CxString::operator+=(char const *)
0x1830688d3  mov     rcx, rsi; this
0x1830688d6  call    ?IsEmpty@CxString@@QEBA_NXZ; CxString::IsEmpty(void)
0x1830688db  test    al, al
0x1830688dd  jnz     loc_183068790
0x1830688e3  mov     rcx, rsi; this
0x1830688e6  call    ?GetCharPointer@CxString@@QEBAPEBDXZ; CxString::GetCharPointer(void)
0x1830688eb  mov     rcx, rax; char *
0x1830688ee  call    ?SetStartupDir@@YAXPEBD@Z; SetStartupDir(char const *)
0x1830688f3  mov     al, 1
0x1830688f5  mov     rcx, [rsp+4A8h+var_28]
0x1830688fd  xor     rcx, rsp; StackCookie
0x183068900  call    __security_check_cookie
0x183068905  mov     rbx, [rsp+4A8h+arg_18]
0x18306890d  add     rsp, 490h
0x183068914  pop     rdi
0x183068915  pop     rsi
0x183068916  pop     rbp
0x183068917  retn
```
