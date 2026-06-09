# DllGetClassObject

- ea: `0x1800281e0`
- end: `0x1800284f8`
- name: `DllGetClassObject`
- size: `792`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002b1c`
- `0x1800277b8`
- `0x1800281e0`
- `0x1804c5304`

## import_xrefs

- `mfc140u!__imp_??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z` at `0x180028205`
- `mfc140u!__imp_??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z` at `0x180028205`
- `mfc140u!__imp_??1AFX_MAINTAIN_STATE2@@QEAA@XZ` at `0x1800284e0`
- `mfc140u!__imp_??1AFX_MAINTAIN_STATE2@@QEAA@XZ` at `0x1800284e0`

## string_xrefs

- `0x180028388`: `LockDelete`
- `0x180028303`: `LockMoveX`
- `0x180028316`: `LockMoveY`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  struct AFX_MODULE_STATE *v6; // rax
  __int64 v7; // rcx
  HRESULT v8; // ebx
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  v6 = (struct AFX_MODULE_STATE *)sub_1804C5304();
  AFX_MAINTAIN_STATE2::AFX_MAINTAIN_STATE2((AFX_MAINTAIN_STATE2 *)v10, v6);
  if ( !byte_1806FF258 )
  {
    byte_1806FF258 = 1;
    sub_180002B1C(&qword_1806FF960);
    sub_180002B1C(&qword_1806FF918);
    sub_180002B1C(qword_1806FF9A0);
    sub_180002B1C(&qword_1806FF890);
    sub_180002B1C(&qword_1806FF928);
    sub_180002B1C(&qword_1806FF8E8);
    sub_180002B1C(&qword_1806FF8A0);
    sub_180002B1C(&qword_1806FF940);
    sub_180002B1C(&qword_1806FF888);
    sub_180002B1C(&qword_1806FF948);
    sub_180002B1C(&qword_1806FF910);
    sub_180002B1C(&qword_1806FF970);
    sub_180002B1C(&qword_1806FF900);
    sub_180002B1C(&qword_1806FF8D0);
    sub_180002B1C(&qword_1806FF980);
    sub_180002B1C(&qword_1806FF988);
    sub_180002B1C(&qword_1806FF8E0);
    sub_180002B1C(&qword_1806FF8D8);
    sub_180002B1C(&qword_1806FF8F0);
    sub_180002B1C(&qword_1806FF898);
    sub_180002B1C(&qword_1806FF8B8);
    sub_180002B1C(&qword_1806FF968);
    sub_180002B1C(&qword_1806FF978);
    sub_180002B1C(&qword_1806FF950);
    sub_180002B1C(&qword_1806FF998);
    sub_180002B1C(&qword_1806FF8B0);
    sub_180002B1C(&qword_1806FF958);
    sub_180002B1C(&qword_1806FF930);
    sub_180002B1C(&qword_1806FF938);
    sub_180002B1C(&qword_1806FF920);
    sub_180002B1C(&qword_1806FF8F8);
    sub_180002B1C(&qword_1806FF8C8);
    sub_180002B1C(&qword_1806FF8C0);
    sub_180002B1C(&qword_1806FF908);
    sub_180002B1C(&qword_1806FF990);
    sub_180002B1C(&qword_1806FF8A8);
  }
  v8 = sub_1800277B8(v7, rclsid, riid, ppv);
  AFX_MAINTAIN_STATE2::~AFX_MAINTAIN_STATE2((AFX_MAINTAIN_STATE2 *)v10);
  return v8;
}

```

## disassembly

```asm
0x1800281e0  mov     [rsp+arg_0], rbx
0x1800281e5  mov     [rsp+arg_8], rsi
0x1800281ea  push    rdi
0x1800281eb  sub     rsp, 30h
0x1800281ef  mov     rbx, r8
0x1800281f2  mov     rdi, rdx
0x1800281f5  mov     rsi, rcx
0x1800281f8  call    sub_1804C5304
0x1800281fd  mov     rdx, rax
0x180028200  lea     rcx, [rsp+38h+var_18]
0x180028205  call    cs:__imp_??0AFX_MAINTAIN_STATE2@@QEAA@PEAVAFX_MODULE_STATE@@@Z; AFX_MAINTAIN_STATE2::AFX_MAINTAIN_STATE2(AFX_MODULE_STATE *)
0x18002820b  cmp     cs:byte_1806FF258, 0
0x180028212  jnz     loc_1800284CB
0x180028218  lea     rdx, aDrawingscale; "DrawingScale"
0x18002821f  mov     cs:byte_1806FF258, 1
0x180028226  lea     rcx, qword_1806FF960
0x18002822d  call    sub_180002B1C
0x180028232  lea     rdx, aHeight; "Height"
0x180028239  lea     rcx, qword_1806FF918
0x180028240  call    sub_180002B1C
0x180028245  lea     rdx, aLocpinx; "LocPinX"
0x18002824c  lea     rcx, qword_1806FF9A0
0x180028253  call    sub_180002B1C
0x180028258  lea     rdx, aLocpiny; "LocPinY"
0x18002825f  lea     rcx, qword_1806FF890
0x180028266  call    sub_180002B1C
0x18002826b  lea     rdx, aPageheight; "PageHeight"
0x180028272  lea     rcx, qword_1806FF928
0x180028279  call    sub_180002B1C
0x18002827e  lea     rdx, aPagescale; "PageScale"
0x180028285  lea     rcx, qword_1806FF8E8
0x18002828c  call    sub_180002B1C
0x180028291  lea     rdx, aPagewidth; "PageWidth"
0x180028298  lea     rcx, qword_1806FF8A0
0x18002829f  call    sub_180002B1C
0x1800282a4  lea     rdx, aPinx; "PinX"
0x1800282ab  lea     rcx, qword_1806FF940
0x1800282b2  call    sub_180002B1C
0x1800282b7  lea     rdx, aPiny; "PinY"
0x1800282be  lea     rcx, qword_1806FF888
0x1800282c5  call    sub_180002B1C
0x1800282ca  lea     rdx, aWidth; "Width"
0x1800282d1  lea     rcx, qword_1806FF948
0x1800282d8  call    sub_180002B1C
0x1800282dd  lea     rdx, aOriginx; "OriginX"
0x1800282e4  lea     rcx, qword_1806FF910
0x1800282eb  call    sub_180002B1C
0x1800282f0  lea     rdx, aOriginy; "OriginY"
0x1800282f7  lea     rcx, qword_1806FF970
0x1800282fe  call    sub_180002B1C
0x180028303  lea     rdx, aLockmovex; "LockMoveX"
0x18002830a  lea     rcx, qword_1806FF900
0x180028311  call    sub_180002B1C
0x180028316  lea     rdx, aLockmovey; "LockMoveY"
0x18002831d  lea     rcx, qword_1806FF8D0
0x180028324  call    sub_180002B1C
0x180028329  lea     rdx, aLockcrop; "LockCrop"
0x180028330  lea     rcx, qword_1806FF980
0x180028337  call    sub_180002B1C
0x18002833c  lea     rdx, aLockwidth; "LockWidth"
0x180028343  lea     rcx, qword_1806FF988
0x18002834a  call    sub_180002B1C
0x18002834f  lea     rdx, aLockheight; "LockHeight"
0x180028356  lea     rcx, qword_1806FF8E0
0x18002835d  call    sub_180002B1C
0x180028362  lea     rdx, aLockaspect; "LockAspect"
0x180028369  lea     rcx, qword_1806FF8D8
0x180028370  call    sub_180002B1C
0x180028375  lea     rdx, aLockrotate; "LockRotate"
0x18002837c  lea     rcx, qword_1806FF8F0
0x180028383  call    sub_180002B1C
0x180028388  lea     rdx, aLockdelete; "LockDelete"
0x18002838f  lea     rcx, qword_1806FF898
0x180028396  call    sub_180002B1C
0x18002839b  lea     rdx, aXrulerorigin; "XRulerOrigin"
0x1800283a2  lea     rcx, qword_1806FF8B8
0x1800283a9  call    sub_180002B1C
0x1800283ae  lea     rdx, aYrulerorigin; "YRulerOrigin"
0x1800283b5  lea     rcx, qword_1806FF968
0x1800283bc  call    sub_180002B1C
0x1800283c1  lea     rdx, aXgridorigin; "XGridOrigin"
0x1800283c8  lea     rcx, qword_1806FF978
0x1800283cf  call    sub_180002B1C
0x1800283d4  lea     rdx, aYgridorigin; "YGridOrigin"
0x1800283db  lea     rcx, qword_1806FF950
0x1800283e2  call    sub_180002B1C
0x1800283e7  lea     rdx, aScratchX1; "Scratch.X1"
0x1800283ee  lea     rcx, qword_1806FF998
0x1800283f5  call    sub_180002B1C
0x1800283fa  lea     rdx, aImgwidth; "ImgWidth"
0x180028401  lea     rcx, qword_1806FF8B0
0x180028408  call    sub_180002B1C
0x18002840d  lea     rdx, aImgheight; "ImgHeight"
0x180028414  lea     rcx, qword_1806FF958
0x18002841b  call    sub_180002B1C
0x180028420  lea     rdx, aImgoffsetx; "ImgOffsetX"
0x180028427  lea     rcx, qword_1806FF930
0x18002842e  call    sub_180002B1C
0x180028433  lea     rdx, aImgoffsety; "ImgOffsetY"
0x18002843a  lea     rcx, qword_1806FF938
0x180028441  call    sub_180002B1C
0x180028446  lea     rdx, a0U; "0.########## u"
0x18002844d  lea     rcx, qword_1806FF920
0x180028454  call    sub_180002B1C
0x180028459  lea     rdx, aCadscalesetbyu_0; "CADScaleSetByUser"
0x180028460  lea     rcx, qword_1806FF8F8
0x180028467  call    sub_180002B1C
0x18002846c  lea     rdx, aCadexportscale; "CADExportScale"
0x180028473  lea     rcx, qword_1806FF8C8
0x18002847a  call    sub_180002B1C
0x18002847f  lea     rdx, aPageleftmargin; "PageLeftMargin"
0x180028486  lea     rcx, qword_1806FF8C0
0x18002848d  call    sub_180002B1C
0x180028492  lea     rdx, aPagerightmargi; "PageRightMargin"
0x180028499  lea     rcx, qword_1806FF908
0x1800284a0  call    sub_180002B1C
0x1800284a5  lea     rdx, aPagetopmargin; "PageTopMargin"
0x1800284ac  lea     rcx, qword_1806FF990
0x1800284b3  call    sub_180002B1C
0x1800284b8  lea     rdx, aPagebottommarg; "PageBottomMargin"
0x1800284bf  lea     rcx, qword_1806FF8A8
0x1800284c6  call    sub_180002B1C
0x1800284cb  mov     r9, rbx
0x1800284ce  mov     r8, rdi
0x1800284d1  mov     rdx, rsi
0x1800284d4  call    sub_1800277B8
0x1800284d9  lea     rcx, [rsp+38h+var_18]
0x1800284de  mov     ebx, eax
0x1800284e0  call    cs:__imp_??1AFX_MAINTAIN_STATE2@@QEAA@XZ; AFX_MAINTAIN_STATE2::~AFX_MAINTAIN_STATE2(void)
0x1800284e6  mov     rsi, [rsp+38h+arg_8]
0x1800284eb  mov     eax, ebx
0x1800284ed  mov     rbx, [rsp+38h+arg_0]
0x1800284f2  add     rsp, 30h
0x1800284f6  pop     rdi
0x1800284f7  retn
```
