# InitGlobal(char *)

- ea: `0x1800246d4`
- end: `0x1800249ac`
- name: `?InitGlobal@@YAJPEAD@Z`
- size: `728`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting`

## callers

- `0x1800245b8`

## callees

- `0x180015ac0`
- `0x180015cf0`
- `0x18001653c`
- `0x18001b8c8`
- `0x18001c654`
- `0x18001cc04`
- `0x1800246d4`
- `0x180024da8`
- `0x18002518c`
- `0x1800255fc`
- `0x1800256b4`
- `0x180025d60`
- `0x180025e60`
- `0x1800260d4`
- `0x1800262b0`
- `0x180026914`
- `0x18002a56c`
- `0x18002ec90`
- `0x18003ec6c`
- `0x180056160`
- `0x18005a8d0`
- `0x180066468`
- `0x1800c6890`
- `0x1800ca014`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x1800247d5`
- `KERNEL32!GetModuleFileNameA` at `0x1800247d5`
- `KERNEL32!SetErrorMode` at `0x18002470e`
- `KERNEL32!SetErrorMode` at `0x18002470e`
- `KERNEL32!GlobalAddAtomA` at `0x18002495a`
- `KERNEL32!GlobalAddAtomA` at `0x18002495a`
- `USER32!LoadCursorA` at `0x180024894`
- `USER32!LoadCursorA` at `0x1800248b1`
- `USER32!LoadCursorA` at `0x180024894`
- `USER32!LoadCursorA` at `0x1800248b1`
- `GDI32!CreateSolidBrush` at `0x1800248db`
- `GDI32!CreateSolidBrush` at `0x1800248db`
- `OLEAUT32!__imp_OaBuildVersion` at `0x180024846`
- `OLEAUT32!__imp_OaBuildVersion` at `0x180024846`

## string_xrefs

- `0x180024855`: `OLEAUT32.DLL`
- `0x180024875`: `OLEAUT32.DLL`

## pseudocode

```c
__int64 __fastcall InitGlobal(char *a1)
{
  __int64 result; // rax
  unsigned int v2; // eax
  HBRUSH SolidBrush; // rax
  unsigned int v4; // eax
  CHAR Filename[2048]; // [rsp+40h] [rbp-818h] BYREF

  _InitModeLogging();
  if ( !Sys_fWin95Shell )
    _LoadCtl3dSupport();
  SetErrorMode(0x8001u);
  if ( !Rby_hIntlLib )
  {
    Rby_hIntlLib = LoadLangDLLMain(0);
    if ( !Rby_hIntlLib )
      goto LABEL_5;
  }
  g_enumStartup = 1;
  if ( !(unsigned int)IntlfCreateFuncTable() )
  {
LABEL_7:
    LODWORD(result) = -2146778287;
    goto LABEL_44;
  }
  if ( lpIntlFuncTable && *(_QWORD *)(lpIntlFuncTable + 136) )
    (*(void (__fastcall **)(struct VBINTLMISC **))(lpIntlFuncTable + 136))(&lpIntlData);
  StrGetNewLcid();
  g_enumStartup = 2;
  if ( lpIntlFuncTable && *(_QWORD *)(lpIntlFuncTable + 24) )
    (*(void (__fastcall **)(_QWORD))(lpIntlFuncTable + 24))(0);
  Sys_fIsBiDi = 0;
  if ( (unsigned int)_CheckBiDi() )
  {
    LODWORD(result) = GetHelpFileNames();
    if ( (int)result < 0 )
      goto LABEL_42;
    if ( !g_fOleAutLoaded )
    {
      GetModuleFileNameA(Rby_hmodThun, Filename, 0x800u);
      if ( !(unsigned int)CFileRep::SetFullPath((CFileRep *)Dlg_filerepModuleDir, Filename) )
        goto LABEL_43;
    }
    RbyGetCwd((struct CFileRep *)g_Dlg_filerepLastPathFiles);
    if ( !(unsigned int)CFileRep::ConvertFullPathToDir((CFileRep *)g_Dlg_filerepLastPathFiles) )
      goto LABEL_43;
    v2 = _CheckDllVersions();
    if ( v2 )
    {
      LODWORD(result) = _HrFromErr(v2);
      if ( (int)result < 0 )
        goto LABEL_42;
    }
    VBEValidateLicense();
    LODWORD(result) = _RbyInitOle();
    if ( (int)result < 0 )
      goto LABEL_42;
    if ( !g_fOleAutLoaded )
    {
      if ( OaBuildVersion() >> 16 < 0x1E )
      {
        ErrorRemember(0x170u, "OLEAUT32.DLL");
        result = _HrFromErr(0x170u);
        goto LABEL_41;
      }
      LoadOleAutDLL("OLEAUT32.DLL", 0);
      g_fOleAutLoaded = 1;
    }
    hcursorArrow = LoadCursorA(0, (LPCSTR)0x7F00);
    if ( !hcursorArrow )
      goto LABEL_43;
    hcursorWait = LoadCursorA(0, (LPCSTR)0x7F02);
    if ( !hcursorWait )
      goto LABEL_43;
    if ( Sys_fWin95Shell )
      SolidBrush = (HBRUSH)25;
    else
      SolidBrush = CreateSolidBrush(0xE1FFFFu);
    if ( !(unsigned int)RbyRegisterClass(
                          "VBBubble",
                          (__int64 (*)(HWND, unsigned int, unsigned __int64, __int64))BubbleWndProc,
                          0,
                          0,
                          SolidBrush,
                          0x800u,
                          0) )
      goto LABEL_7;
    if ( lpCtl3dAutoSubclass )
      lpCtl3dAutoSubclass(Rby_hinstExe);
    InitProgressBar();
    LODWORD(result) = ProjInitProjCode();
    if ( (int)result < 0 )
      goto LABEL_42;
    v4 = RefInit();
    if ( v4 )
    {
      LODWORD(result) = _HrFromErr(v4);
      if ( (int)result < 0 )
        goto LABEL_42;
    }
    if ( !Rby_atomVBDisabled )
      Rby_atomVBDisabled = GlobalAddAtomA("VBDisabled");
    LODWORD(result) = ProjFInitClass();
    if ( (int)result < 0 )
    {
LABEL_42:
      if ( (_DWORD)result != -2147024882 )
        goto LABEL_44;
LABEL_43:
      LODWORD(result) = -2146778286;
      goto LABEL_44;
    }
    result = 0;
LABEL_41:
    if ( (int)result >= 0 )
      return result;
    goto LABEL_42;
  }
LABEL_5:
  LODWORD(result) = -2146768289;
LABEL_44:
  ErrorHr(result);
  InitTermGlobal();
  return 2148199007LL;
}

```

## disassembly

```asm
0x1800246d4  push    rdi
0x1800246d6  mov     eax, 850h
0x1800246db  call    _alloca_probe
0x1800246e0  sub     rsp, rax
0x1800246e3  mov     rax, cs:__security_cookie
0x1800246ea  xor     rax, rsp
0x1800246ed  mov     [rsp+858h+var_18], rax
0x1800246f5  call    ?_InitModeLogging@@YAXXZ; _InitModeLogging(void)
0x1800246fa  xor     edi, edi
0x1800246fc  cmp     cs:?Sys_fWin95Shell@@3HA, edi; int Sys_fWin95Shell
0x180024702  jnz     short loc_180024709
0x180024704  call    ?_LoadCtl3dSupport@@YAXXZ; _LoadCtl3dSupport(void)
0x180024709  mov     ecx, 8001h; uMode
0x18002470e  call    cs:__imp_SetErrorMode
0x180024714  cmp     cs:?Rby_hIntlLib@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * Rby_hIntlLib
0x18002471b  jnz     short loc_18002473A
0x18002471d  xor     ecx, ecx; int
0x18002471f  call    ?LoadLangDLLMain@@YAPEAUHINSTANCE__@@H@Z; LoadLangDLLMain(int)
0x180024724  mov     cs:?Rby_hIntlLib@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Rby_hIntlLib
0x18002472b  test    rax, rax
0x18002472e  jnz     short loc_18002473A
0x180024730  mov     eax, 800AEA5Fh
0x180024735  jmp     loc_180024982
0x18002473a  mov     cs:?g_enumStartup@@3W4STARTUPSTATUS@@A, 1; STARTUPSTATUS g_enumStartup
0x180024744  call    ?IntlfCreateFuncTable@@YAHXZ; IntlfCreateFuncTable(void)
0x180024749  test    eax, eax
0x18002474b  jnz     short loc_180024757
0x18002474d  mov     eax, 800AC351h
0x180024752  jmp     loc_180024982
0x180024757  mov     rax, cs:?lpIntlFuncTable@@3PEAP6AXZZEA; void (** lpIntlFuncTable)(...)
0x18002475e  test    rax, rax
0x180024761  jz      short loc_180024779
0x180024763  cmp     [rax+88h], rdi
0x18002476a  jz      short loc_180024779
0x18002476c  lea     rcx, ?lpIntlData@@3PEAUVBINTLMISC@@EA; VBINTLMISC * lpIntlData
0x180024773  call    qword ptr [rax+88h]
0x180024779  call    ?StrGetNewLcid@@YAXXZ; StrGetNewLcid(void)
0x18002477e  mov     rax, cs:?lpIntlFuncTable@@3PEAP6AXZZEA; void (** lpIntlFuncTable)(...)
0x180024785  mov     cs:?g_enumStartup@@3W4STARTUPSTATUS@@A, 2; STARTUPSTATUS g_enumStartup
0x18002478f  test    rax, rax
0x180024792  jz      short loc_18002479F
0x180024794  cmp     [rax+18h], rdi
0x180024798  jz      short loc_18002479F
0x18002479a  xor     ecx, ecx
0x18002479c  call    qword ptr [rax+18h]
0x18002479f  mov     cs:?Sys_fIsBiDi@@3HA, edi; int Sys_fIsBiDi
0x1800247a5  call    ?_CheckBiDi@@YAHXZ; _CheckBiDi(void)
0x1800247aa  test    eax, eax
0x1800247ac  jz      short loc_180024730
0x1800247ae  call    ?GetHelpFileNames@@YAJXZ; GetHelpFileNames(void)
0x1800247b3  test    eax, eax
0x1800247b5  js      loc_180024976
0x1800247bb  cmp     cs:?g_fOleAutLoaded@@3HA, edi; int g_fOleAutLoaded
0x1800247c1  jnz     short loc_1800247F4
0x1800247c3  mov     rcx, cs:?Rby_hmodThun@@3PEAUHINSTANCE__@@EA; hModule
0x1800247ca  lea     rdx, [rsp+858h+Filename]; lpFilename
0x1800247cf  mov     r8d, 800h; nSize
0x1800247d5  call    cs:__imp_GetModuleFileNameA
0x1800247db  lea     rdx, [rsp+858h+Filename]; char *
0x1800247e0  lea     rcx, ?Dlg_filerepModuleDir@@3VCFileRep@@A; this
0x1800247e7  call    ?SetFullPath@CFileRep@@QEAAHPEBD@Z; CFileRep::SetFullPath(char const *)
0x1800247ec  test    eax, eax
0x1800247ee  jz      loc_18002497D
0x1800247f4  lea     rcx, ?g_Dlg_filerepLastPathFiles@@3VCFileRep@@A; struct CFileRep *
0x1800247fb  call    ?RbyGetCwd@@YAHPEAVCFileRep@@@Z; RbyGetCwd(CFileRep *)
0x180024800  lea     rcx, ?g_Dlg_filerepLastPathFiles@@3VCFileRep@@A; this
0x180024807  call    ?ConvertFullPathToDir@CFileRep@@QEAAHXZ; CFileRep::ConvertFullPathToDir(void)
0x18002480c  test    eax, eax
0x18002480e  jz      loc_18002497D
0x180024814  call    ?_CheckDllVersions@@YAIXZ; _CheckDllVersions(void)
0x180024819  test    eax, eax
0x18002481b  jz      short loc_18002482C
0x18002481d  mov     ecx, eax; unsigned int
0x18002481f  call    ?_HrFromErr@@YAJI@Z; _HrFromErr(uint)
0x180024824  test    eax, eax
0x180024826  js      loc_180024976
0x18002482c  call    ?VBEValidateLicense@@YAXXZ; VBEValidateLicense(void)
0x180024831  call    ?_RbyInitOle@@YAJXZ; _RbyInitOle(void)
0x180024836  test    eax, eax
0x180024838  js      loc_180024976
0x18002483e  cmp     cs:?g_fOleAutLoaded@@3HA, edi; int g_fOleAutLoaded
0x180024844  jnz     short loc_18002488D
0x180024846  call    cs:__imp_OaBuildVersion
0x18002484c  shr     eax, 10h
0x18002484f  cmp     ax, 1Eh
0x180024853  jnb     short loc_180024875
0x180024855  lea     rdx, aOleaut32Dll_2; "OLEAUT32.DLL"
0x18002485c  mov     ecx, 170h; unsigned int
0x180024861  call    ?ErrorRemember@@YAIIPEBD@Z; ErrorRemember(uint,char const *)
0x180024866  mov     ecx, 170h; unsigned int
0x18002486b  call    ?_HrFromErr@@YAJI@Z; _HrFromErr(uint)
0x180024870  jmp     loc_180024972
0x180024875  lea     rcx, aOleaut32Dll_0; "OLEAUT32.DLL"
0x18002487c  xor     edx, edx; int
0x18002487e  call    ?LoadOleAutDLL@@YAIPEADH@Z; LoadOleAutDLL(char *,int)
0x180024883  mov     cs:?g_fOleAutLoaded@@3HA, 1; int g_fOleAutLoaded
0x18002488d  mov     edx, 7F00h; lpCursorName
0x180024892  xor     ecx, ecx; hInstance
0x180024894  call    cs:__imp_LoadCursorA
0x18002489a  mov     cs:?hcursorArrow@@3PEAUHICON__@@EA, rax; HICON__ * hcursorArrow
0x1800248a1  test    rax, rax
0x1800248a4  jz      loc_18002497D
0x1800248aa  mov     edx, 7F02h; lpCursorName
0x1800248af  xor     ecx, ecx; hInstance
0x1800248b1  call    cs:__imp_LoadCursorA
0x1800248b7  mov     cs:?hcursorWait@@3PEAUHICON__@@EA, rax; HICON__ * hcursorWait
0x1800248be  test    rax, rax
0x1800248c1  jz      loc_18002497D
0x1800248c7  cmp     cs:?Sys_fWin95Shell@@3HA, edi; int Sys_fWin95Shell
0x1800248cd  jz      short loc_1800248D6
0x1800248cf  mov     eax, 19h
0x1800248d4  jmp     short loc_1800248E1
0x1800248d6  mov     ecx, 0E1FFFFh; color
0x1800248db  call    cs:__imp_CreateSolidBrush
0x1800248e1  mov     [rsp+858h+var_828], edi; int
0x1800248e5  lea     rdx, ?BubbleWndProc@@YA_JPEAUHWND__@@I_K_J@Z; __int64 (*)(HWND, unsigned int, unsigned __int64, __int64)
0x1800248ec  lea     rcx, ?szBubbleClass@@3QBDB; "VBBubble"
0x1800248f3  xor     r9d, r9d; HICON
0x1800248f6  xor     r8d, r8d; HICON
0x1800248f9  mov     [rsp+858h+var_830], 800h; unsigned int
0x180024901  mov     [rsp+858h+var_838], rax; HBRUSH
0x180024906  call    ?RbyRegisterClass@@YAHPEBDP6A_JPEAUHWND__@@I_K_J@ZPEAUHICON__@@5PEAUHBRUSH__@@IH@Z; RbyRegisterClass(char const *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),HICON__ *,HICON__ *,HBRUSH__ *,uint,int)
0x18002490b  test    eax, eax
0x18002490d  jz      loc_18002474D
0x180024913  mov     rax, cs:?lpCtl3dAutoSubclass@@3P6AHPEAX@ZEA; int (*lpCtl3dAutoSubclass)(void *)
0x18002491a  test    rax, rax
0x18002491d  jz      short loc_180024928
0x18002491f  mov     rcx, cs:?Rby_hinstExe@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * Rby_hinstExe
0x180024926  call    rax ; int (*lpCtl3dAutoSubclass)(void *)
0x180024928  call    ?InitProgressBar@@YAXXZ; InitProgressBar(void)
0x18002492d  call    ?ProjInitProjCode@@YAJXZ; ProjInitProjCode(void)
0x180024932  test    eax, eax
0x180024934  js      short loc_180024976
0x180024936  call    ?RefInit@@YAIXZ; RefInit(void)
0x18002493b  test    eax, eax
0x18002493d  jz      short loc_18002494A
0x18002493f  mov     ecx, eax; unsigned int
0x180024941  call    ?_HrFromErr@@YAJI@Z; _HrFromErr(uint)
0x180024946  test    eax, eax
0x180024948  js      short loc_180024976
0x18002494a  cmp     cs:?Rby_atomVBDisabled@@3GA, di; ushort Rby_atomVBDisabled
0x180024951  jnz     short loc_180024967
0x180024953  lea     rcx, aVbdisabled; "VBDisabled"
0x18002495a  call    cs:__imp_GlobalAddAtomA
0x180024960  mov     cs:?Rby_atomVBDisabled@@3GA, ax; ushort Rby_atomVBDisabled
0x180024967  call    ?ProjFInitClass@@YAJXZ; ProjFInitClass(void)
0x18002496c  test    eax, eax
0x18002496e  js      short loc_180024976
0x180024970  mov     eax, edi
0x180024972  test    eax, eax
0x180024974  jns     short loc_180024993
0x180024976  cmp     eax, 8007000Eh
0x18002497b  jnz     short loc_180024982
0x18002497d  mov     eax, 800AC352h
0x180024982  mov     ecx, eax; int
0x180024984  call    ?ErrorHr@@YAXJ@Z; ErrorHr(long)
0x180024989  call    ?InitTermGlobal@@YAXXZ; InitTermGlobal(void)
0x18002498e  mov     eax, 800AEA5Fh
0x180024993  mov     rcx, [rsp+858h+var_18]
0x18002499b  xor     rcx, rsp; StackCookie
0x18002499e  call    __security_check_cookie
0x1800249a3  add     rsp, 850h
0x1800249aa  pop     rdi
0x1800249ab  retn
```
