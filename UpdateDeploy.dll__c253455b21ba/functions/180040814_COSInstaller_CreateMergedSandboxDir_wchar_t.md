# COSInstaller::CreateMergedSandboxDir(wchar_t * *)

- ea: `0x180040814`
- end: `0x180040a35`
- name: `?CreateMergedSandboxDir@COSInstaller@@AEAAJPEAPEA_W@Z`
- size: `545`
- prototype: `__int64 __fastcall(COSInstaller *this, wchar_t **, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003fd7c`

## callees

- `0x180003180`
- `0x18000c640`
- `0x18000dce4`
- `0x180040814`
- `0x180049130`
- `0x180049ff8`
- `0x18004bd90`
- `0x180061960`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x1800408ff`
- `RPCRT4!UuidToStringW` at `0x1800408ff`
- `RPCRT4!UuidCreate` at `0x1800408b9`
- `RPCRT4!UuidCreate` at `0x1800408b9`

## string_xrefs

- `0x18004094d`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18004098e`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x1800409cb`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180040893`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x180040875`: `MergedUpdates`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall COSInstaller::CreateMergedSandboxDir(COSInstaller *this, wchar_t **a2, __int64 a3, unsigned int *a4)
{
  wchar_t *v4; // rbx
  WCHAR *v5; // rdi
  unsigned int v7; // esi
  __int64 v8; // rdx
  int SusBaseDirectoryW; // eax
  unsigned __int64 v10; // r9
  RPC_STATUS v11; // eax
  RPC_STATUS v12; // eax
  int v13; // eax
  int CombinedPath; // eax
  __int64 v15; // rdx
  void *v16; // r8
  int DirectoryW; // eax
  wchar_t *v18; // rax
  wchar_t *v20; // [rsp+20h] [rbp-E0h] BYREF
  PCNZWCH lpString1; // [rsp+28h] [rbp-D8h] BYREF
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-D0h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t v24[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = 0;
  StringUuid = 0;
  v5 = 0;
  v20 = 0;
  lpString1 = 0;
  Uuid = 0;
  if ( !a2 )
  {
    v7 = -2147467261;
    v8 = 1909;
LABEL_5:
    v10 = v7;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v10,
      (int)v20);
    goto LABEL_22;
  }
  SusBaseDirectoryW = GetSusBaseDirectoryW(v24, (unsigned int)a2, L"MergedUpdates", a4);
  v7 = SusBaseDirectoryW;
  if ( SusBaseDirectoryW < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
      (const char *)(unsigned int)SusBaseDirectoryW,
      (int)v20);
    v8 = 1912;
    goto LABEL_5;
  }
  v11 = UuidCreate(&Uuid);
  if ( v11 )
  {
    v7 = (unsigned __int16)v11 | 0x80070000;
    if ( v11 <= 0 )
      v7 = v11;
    v10 = v7;
    v8 = 1919;
    goto LABEL_20;
  }
  v12 = UuidToStringW(&Uuid, &StringUuid);
  if ( v12 )
  {
    v7 = (unsigned __int16)v12 | 0x80070000;
    if ( v12 <= 0 )
      v7 = v12;
    v10 = v7;
    v8 = 1924;
    goto LABEL_20;
  }
  v13 = CreateCombinedPath(v24, StringUuid, &v20);
  v7 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)v13,
      (int)v20);
    v4 = v20;
    goto LABEL_22;
  }
  v4 = v20;
  CombinedPath = CreateCombinedPath(v20, L"Metadata", (wchar_t **)&lpString1);
  v7 = CombinedPath;
  if ( CombinedPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)(unsigned int)CombinedPath,
      (int)v20);
    v5 = (WCHAR *)lpString1;
    goto LABEL_22;
  }
  v5 = (WCHAR *)lpString1;
  DirectoryW = SusMakeDirectoryW(lpString1, v15, v16);
  v7 = DirectoryW;
  if ( DirectoryW < 0 )
  {
    v10 = (unsigned int)DirectoryW;
    v8 = 1936;
    goto LABEL_20;
  }
  v18 = v4;
  v4 = 0;
  v7 = 0;
  *a2 = v18;
LABEL_22:
  if ( v5 )
    SusFree(v5);
  if ( v4 )
    SusFree(v4);
  if ( StringUuid )
    XPtrRpcStringFree(StringUuid);
  return v7;
}

```

## disassembly

```asm
0x180040814  mov     [rsp-8+arg_0], rbx
0x180040819  mov     [rsp-8+arg_10], rsi
0x18004081e  push    rbp
0x18004081f  push    rdi
0x180040820  push    r14
0x180040822  lea     rbp, [rsp-170h]
0x18004082a  sub     rsp, 270h
0x180040831  mov     rax, cs:__security_cookie
0x180040838  xor     rax, rsp
0x18004083b  mov     [rbp+180h+var_20], rax
0x180040842  xor     ebx, ebx
0x180040844  mov     [rsp+280h+StringUuid], 0
0x18004084d  xor     edi, edi
0x18004084f  mov     [rsp+280h+var_260], rbx; int
0x180040854  mov     [rsp+280h+lpString1], rdi
0x180040859  xorps   xmm0, xmm0
0x18004085c  mov     r14, rdx
0x18004085f  movups  xmmword ptr [rsp+280h+Uuid.Data1], xmm0
0x180040864  test    rdx, rdx
0x180040867  jnz     short loc_180040875
0x180040869  mov     esi, 80004003h
0x18004086e  mov     edx, 775h; unsigned int
0x180040873  jmp     short loc_1800408AC
0x180040875  lea     r8, aMergedupdates; "MergedUpdates"
0x18004087c  lea     rcx, [rsp+280h+var_230]; wchar_t *
0x180040881  call    ?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z; GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)
0x180040886  mov     esi, eax
0x180040888  test    eax, eax
0x18004088a  jns     short loc_1800408B4
0x18004088c  mov     rcx, [rbp+188h]; this
0x180040893  lea     r8, aCW1SSrcClientL_19; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004089a  mov     r9d, eax; char *
0x18004089d  mov     edx, 0B6h; void *
0x1800408a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800408a7  mov     edx, 778h
0x1800408ac  mov     r9d, esi
0x1800408af  jmp     loc_1800409C4
0x1800408b4  lea     rcx, [rsp+280h+Uuid]; Uuid
0x1800408b9  call    cs:__imp_UuidCreate
0x1800408bf  test    eax, eax
0x1800408c1  jz      short loc_1800408E6
0x1800408c3  movzx   esi, ax
0x1800408c6  or      esi, 80070000h
0x1800408cc  test    eax, eax
0x1800408ce  cmovle  esi, eax
0x1800408d1  test    esi, esi
0x1800408d3  jns     loc_1800409E3
0x1800408d9  mov     r9d, esi
0x1800408dc  mov     edx, 77Fh
0x1800408e1  jmp     loc_1800409C4
0x1800408e6  mov     rcx, [rsp+280h+StringUuid]; void *
0x1800408eb  test    rcx, rcx
0x1800408ee  jz      short loc_1800408F5
0x1800408f0  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x1800408f5  lea     rdx, [rsp+280h+StringUuid]; StringUuid
0x1800408fa  lea     rcx, [rsp+280h+Uuid]; Uuid
0x1800408ff  call    cs:__imp_UuidToStringW
0x180040905  test    eax, eax
0x180040907  jz      short loc_18004092C
0x180040909  movzx   esi, ax
0x18004090c  or      esi, 80070000h
0x180040912  test    eax, eax
0x180040914  cmovle  esi, eax
0x180040917  test    esi, esi
0x180040919  jns     loc_1800409E3
0x18004091f  mov     r9d, esi
0x180040922  mov     edx, 784h
0x180040927  jmp     loc_1800409C4
0x18004092c  mov     rdx, [rsp+280h+StringUuid]; wchar_t *
0x180040931  lea     r8, [rsp+280h+var_260]; wchar_t **
0x180040936  lea     rcx, [rsp+280h+var_230]; wchar_t *
0x18004093b  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x180040940  mov     esi, eax
0x180040942  test    eax, eax
0x180040944  jns     short loc_180040968
0x180040946  mov     rcx, [rbp+188h]; this
0x18004094d  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180040954  mov     r9d, eax; char *
0x180040957  mov     edx, 788h; void *
0x18004095c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040961  mov     rbx, [rsp+280h+var_260]
0x180040966  jmp     short loc_1800409E3
0x180040968  mov     rbx, [rsp+280h+var_260]
0x18004096d  lea     r8, [rsp+280h+lpString1]; wchar_t **
0x180040972  mov     rcx, rbx; wchar_t *
0x180040975  lea     rdx, ?c_szUUPMetaDataSubFolder@CDeploymentSessionWrapper@OSDeploymentHelper@@2QB_WB; "Metadata"
0x18004097c  call    ?CreateCombinedPath@@YAJPEB_W0PEAPEA_W@Z; CreateCombinedPath(wchar_t const *,wchar_t const *,wchar_t * *)
0x180040981  mov     esi, eax
0x180040983  test    eax, eax
0x180040985  jns     short loc_1800409A9
0x180040987  mov     rcx, [rbp+188h]; this
0x18004098e  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180040995  mov     r9d, eax; char *
0x180040998  mov     edx, 78Dh; void *
0x18004099d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800409a2  mov     rdi, [rsp+280h+lpString1]
0x1800409a7  jmp     short loc_1800409E3
0x1800409a9  mov     rdi, [rsp+280h+lpString1]
0x1800409ae  mov     rcx, rdi; lpString1
0x1800409b1  call    ?SusMakeDirectoryW@@YAJPEB_WKPEAX@Z; SusMakeDirectoryW(wchar_t const *,ulong,void *)
0x1800409b6  mov     esi, eax
0x1800409b8  test    eax, eax
0x1800409ba  jns     short loc_1800409D9
0x1800409bc  mov     r9d, eax; char *
0x1800409bf  mov     edx, 790h; void *
0x1800409c4  mov     rcx, [rbp+188h]; this
0x1800409cb  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800409d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800409d7  jmp     short loc_1800409E3
0x1800409d9  mov     rax, rbx
0x1800409dc  xor     ebx, ebx
0x1800409de  xor     esi, esi
0x1800409e0  mov     [r14], rax
0x1800409e3  test    rdi, rdi
0x1800409e6  jz      short loc_1800409F0
0x1800409e8  mov     rcx, rdi; lpMem
0x1800409eb  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800409f0  test    rbx, rbx
0x1800409f3  jz      short loc_1800409FD
0x1800409f5  mov     rcx, rbx; lpMem
0x1800409f8  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800409fd  mov     rcx, [rsp+280h+StringUuid]; void *
0x180040a02  test    rcx, rcx
0x180040a05  jz      short loc_180040A0C
0x180040a07  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x180040a0c  mov     eax, esi
0x180040a0e  mov     rcx, [rbp+180h+var_20]
0x180040a15  xor     rcx, rsp; StackCookie
0x180040a18  call    __security_check_cookie
0x180040a1d  lea     r11, [rsp+280h+var_10]
0x180040a25  mov     rbx, [r11+20h]
0x180040a29  mov     rsi, [r11+30h]
0x180040a2d  mov     rsp, r11
0x180040a30  pop     r14
0x180040a32  pop     rdi
0x180040a33  pop     rbp
0x180040a34  retn
```
