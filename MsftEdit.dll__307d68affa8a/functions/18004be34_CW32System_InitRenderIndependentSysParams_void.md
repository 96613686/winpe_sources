# CW32System::InitRenderIndependentSysParams(void)

- ea: `0x18004be34`
- end: `0x18004bf80`
- name: `?InitRenderIndependentSysParams@CW32System@@SAXXZ`
- size: `332`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18004af24`
- `0x18004bd68`

## callees

- `0x18004bcf0`
- `0x18004be34`
- `0x18004c914`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004be72`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004be81`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004be8f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004be98`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004bea1`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004beb0`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004be72`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004be81`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004be8f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004be98`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004bea1`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004beb0`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18004bf0f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18004bf3e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18004bf5e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18004bf0f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18004bf3e`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18004bf5e`
- `ext-ms-win-ntuser-mouse-l1-1-0!GetDoubleClickTime` at `0x18004bebc`
- `ext-ms-win-ntuser-mouse-l1-1-0!GetDoubleClickTime` at `0x18004bebc`

## pseudocode

```c
void CW32System::InitRenderIndependentSysParams(void)
{
  bool v0; // cl
  bool v1; // al
  int pvParam; // [rsp+30h] [rbp+8h] BYREF
  int v3; // [rsp+38h] [rbp+10h] BYREF
  int v4; // [rsp+40h] [rbp+18h] BYREF

  CW32System::_nScrollInset = 11;
  CW32System::_nDragDelay = 200;
  CW32System::_nDragMinDist = 2;
  CW32System::_nScrollDelay = 50;
  CW32System::_nScrollInterval = 50;
  CW32System::_cxBorder = GetSystemMetrics(5);
  CW32System::_cyBorder = GetSystemMetrics(6);
  GetSystemMetrics(2);
  GetSystemMetrics(3);
  CW32System::_cxDoubleClk = GetSystemMetrics(36);
  CW32System::_cyDoubleClk = GetSystemMetrics(37);
  CW32System::_DCT = GetDoubleClickTime();
  CW32System::_sysiniflags = 0;
  CW32System::_bDigitSubstMode = CW32System::ReadRegDigitSubstitutionMode();
  if ( !CW32System::_draftModeFontInfo )
    word_1802DF1EA = 0;
  CW32System::_dupCaret = CW32System::GetSystemCaretWidth(v0);
  pvParam = 0;
  SystemParametersInfoW(0x1Bu, 0, &pvParam, 0);
  v3 = 0;
  CW32System::_fRightHanded = pvParam != 0;
  v4 = 0;
  v1 = SystemParametersInfoW(0x4Au, 0, &v3, 0) && v3 && SystemParametersInfoW(0x200Au, 0, &v4, 0) && v4 == 2;
  CW32System::_fClearTypeIsOn = v1;
}

```

## disassembly

```asm
0x18004be34  push    rdi
0x18004be36  sub     rsp, 20h
0x18004be3a  mov     eax, 0Bh
0x18004be3f  mov     edi, 2
0x18004be44  mov     cs:?_nScrollInset@CW32System@@0GA, ax; ushort CW32System::_nScrollInset
0x18004be4b  mov     eax, 0C8h
0x18004be50  mov     cs:?_nDragDelay@CW32System@@0GA, ax; ushort CW32System::_nDragDelay
0x18004be57  mov     cs:?_nDragMinDist@CW32System@@0GA, di; ushort CW32System::_nDragMinDist
0x18004be5e  lea     eax, [rdi+30h]
0x18004be61  lea     ecx, [rdi+3]; nIndex
0x18004be64  mov     cs:?_nScrollDelay@CW32System@@0GA, ax; ushort CW32System::_nScrollDelay
0x18004be6b  mov     cs:?_nScrollInterval@CW32System@@0GA, ax; ushort CW32System::_nScrollInterval
0x18004be72  call    cs:__imp_GetSystemMetrics
0x18004be78  lea     ecx, [rdi+4]; nIndex
0x18004be7b  mov     cs:?_cxBorder@CW32System@@0HA, eax; int CW32System::_cxBorder
0x18004be81  call    cs:__imp_GetSystemMetrics
0x18004be87  mov     ecx, edi; nIndex
0x18004be89  mov     cs:?_cyBorder@CW32System@@0HA, eax; int CW32System::_cyBorder
0x18004be8f  call    cs:__imp_GetSystemMetrics
0x18004be95  lea     ecx, [rdi+1]; nIndex
0x18004be98  call    cs:__imp_GetSystemMetrics
0x18004be9e  lea     ecx, [rdi+22h]; nIndex
0x18004bea1  call    cs:__imp_GetSystemMetrics
0x18004bea7  lea     ecx, [rdi+23h]; nIndex
0x18004beaa  mov     cs:?_cxDoubleClk@CW32System@@0HA, eax; int CW32System::_cxDoubleClk
0x18004beb0  call    cs:__imp_GetSystemMetrics
0x18004beb6  mov     cs:?_cyDoubleClk@CW32System@@0HA, eax; int CW32System::_cyDoubleClk
0x18004bebc  call    cs:__imp_GetDoubleClickTime
0x18004bec2  mov     cs:?_DCT@CW32System@@0HA, eax; int CW32System::_DCT
0x18004bec8  mov     cs:?_sysiniflags@CW32System@@0HA, 0; int CW32System::_sysiniflags
0x18004bed2  call    ?ReadRegDigitSubstitutionMode@CW32System@@SAEXZ; CW32System::ReadRegDigitSubstitutionMode(void)
0x18004bed7  cmp     cs:?_draftModeFontInfo@CW32System@@0UDraftModeFontInfo@1@A, 0; CW32System::DraftModeFontInfo CW32System::_draftModeFontInfo
0x18004bede  mov     cs:?_bDigitSubstMode@CW32System@@0EA, al; uchar CW32System::_bDigitSubstMode
0x18004bee4  jnz     short loc_18004BEEF
0x18004bee6  xor     eax, eax
0x18004bee8  mov     cs:word_1802DF1EA, ax
0x18004beef  call    ?GetSystemCaretWidth@CW32System@@SAE_N@Z; CW32System::GetSystemCaretWidth(bool)
0x18004bef4  xor     edx, edx; uiParam
0x18004bef6  mov     cs:?_dupCaret@CW32System@@2EA, al; uchar CW32System::_dupCaret
0x18004befc  xor     r9d, r9d; fWinIni
0x18004beff  mov     [rsp+28h+pvParam], 0
0x18004bf07  lea     r8, [rsp+28h+pvParam]; pvParam
0x18004bf0c  lea     ecx, [rdx+1Bh]; uiAction
0x18004bf0f  call    cs:__imp_SystemParametersInfoW
0x18004bf15  cmp     [rsp+28h+pvParam], 0
0x18004bf1a  lea     r8, [rsp+28h+arg_8]; pvParam
0x18004bf1f  mov     [rsp+28h+arg_8], 0
0x18004bf27  setnz   cs:?_fRightHanded@CW32System@@0EA; uchar CW32System::_fRightHanded
0x18004bf2e  mov     [rsp+28h+arg_10], 0
0x18004bf36  xor     edx, edx; uiParam
0x18004bf38  xor     r9d, r9d; fWinIni
0x18004bf3b  lea     ecx, [rdx+4Ah]; uiAction
0x18004bf3e  call    cs:__imp_SystemParametersInfoW
0x18004bf44  test    eax, eax
0x18004bf46  jz      short loc_18004BF68
0x18004bf48  cmp     [rsp+28h+arg_8], 0
0x18004bf4d  jz      short loc_18004BF68
0x18004bf4f  xor     r9d, r9d; fWinIni
0x18004bf52  lea     r8, [rsp+28h+arg_10]; pvParam
0x18004bf57  xor     edx, edx; uiParam
0x18004bf59  mov     ecx, 200Ah; uiAction
0x18004bf5e  call    cs:__imp_SystemParametersInfoW
0x18004bf64  test    eax, eax
0x18004bf66  jnz     short loc_18004BF76
0x18004bf68  xor     al, al
0x18004bf6a  mov     cs:?_fClearTypeIsOn@CW32System@@2EA, al; uchar CW32System::_fClearTypeIsOn
0x18004bf70  add     rsp, 20h
0x18004bf74  pop     rdi
0x18004bf75  retn
0x18004bf76  cmp     [rsp+28h+arg_10], edi
0x18004bf7a  jnz     short loc_18004BF68
0x18004bf7c  mov     al, 1
0x18004bf7e  jmp     short loc_18004BF6A
```
