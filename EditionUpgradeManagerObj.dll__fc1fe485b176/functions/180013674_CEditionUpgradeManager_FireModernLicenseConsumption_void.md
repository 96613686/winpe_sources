# CEditionUpgradeManager::FireModernLicenseConsumption(void)

- ea: `0x180013674`
- end: `0x180013778`
- name: `?FireModernLicenseConsumption@CEditionUpgradeManager@@AEAAJXZ`
- size: `260`
- prototype: `__int64 __fastcall(CEditionUpgradeManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f264`

## callees

- `0x180001008`
- `0x180001ac0`
- `0x1800090dc`
- `0x180009480`
- `0x180013674`

## import_xrefs

- `SLC!SLOpen` at `0x18001369a`
- `SLC!SLOpen` at `0x18001369a`
- `SLC!SLClose` at `0x18001375a`
- `SLC!SLClose` at `0x18001375a`
- `SLC!SLConsumeRight` at `0x1800136c1`
- `SLC!SLConsumeRight` at `0x1800136c1`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeManager::FireModernLicenseConsumption(CEditionUpgradeManager *this)
{
  HRESULT v1; // ebx
  HRESULT v3; // [rsp+30h] [rbp-58h] BYREF
  HSLC phSLC; // [rsp+38h] [rbp-50h] BYREF
  char v5[32]; // [rsp+40h] [rbp-48h] BYREF
  HRESULT *v6; // [rsp+60h] [rbp-28h]
  __int64 v7; // [rsp+68h] [rbp-20h]

  phSLC = 0;
  v1 = SLOpen(&phSLC);
  if ( v1 < 0 || (v1 = SLConsumeRight(phSLC, &WINDOWS_SLID, 0, 0, 0), v1 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v1);
    if ( (unsigned int)dword_18002F1D0 > 5
      && (qword_18002F1E0 & 0x400000000000LL) != 0
      && (qword_18002F1E8 & 0x400000000000LL) == qword_18002F1E8 )
    {
      v3 = v1;
      v6 = &v3;
      v7 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18002F1D0, &word_18002B10E, 0, 0, 3, v5);
    }
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v1);
  if ( phSLC )
    SLClose(phSLC);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180013674  push    rbx
0x180013676  sub     rsp, 80h
0x18001367d  mov     rax, cs:__security_cookie
0x180013684  xor     rax, rsp
0x180013687  mov     [rsp+88h+var_18], rax
0x18001368c  lea     rcx, [rsp+88h+phSLC]; phSLC
0x180013691  mov     [rsp+88h+phSLC], 0
0x18001369a  call    cs:__imp_SLOpen
0x1800136a0  mov     ebx, eax
0x1800136a2  test    eax, eax
0x1800136a4  js      short loc_1800136CD
0x1800136a6  mov     rcx, [rsp+88h+phSLC]; hSLC
0x1800136ab  lea     rdx, WINDOWS_SLID; pAppId
0x1800136b2  xor     r9d, r9d; pwszRightName
0x1800136b5  mov     [rsp+88h+pvReserved], 0; pvReserved
0x1800136be  xor     r8d, r8d; pProductSkuId
0x1800136c1  call    cs:__imp_SLConsumeRight
0x1800136c7  mov     ebx, eax
0x1800136c9  test    eax, eax
0x1800136cb  jns     short loc_180013749
0x1800136cd  mov     ecx, ebx
0x1800136cf  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800136d4  mov     ecx, cs:dword_18002F1D0
0x1800136da  cmp     ecx, 5
0x1800136dd  jbe     short loc_180013749
0x1800136df  mov     rcx, cs:qword_18002F1E8
0x1800136e6  mov     rdx, 400000000000h
0x1800136f0  mov     rax, cs:qword_18002F1E0
0x1800136f7  test    rdx, rax
0x1800136fa  jz      short loc_180013749
0x1800136fc  mov     rax, rcx
0x1800136ff  and     rax, rdx
0x180013702  cmp     rax, rcx
0x180013705  jnz     short loc_180013749
0x180013707  lea     rax, [rsp+88h+var_58]
0x18001370c  mov     [rsp+88h+var_58], ebx
0x180013710  mov     [rsp+88h+var_28], rax
0x180013715  lea     rdx, word_18002B10E
0x18001371c  lea     rax, [rsp+88h+var_48]
0x180013721  mov     [rsp+88h+var_20], 4
0x18001372a  mov     [rsp+88h+var_60], rax
0x18001372f  lea     rcx, dword_18002F1D0
0x180013736  xor     r9d, r9d
0x180013739  mov     dword ptr [rsp+88h+pvReserved], 3
0x180013741  xor     r8d, r8d
0x180013744  call    _tlgWriteTransfer_EventWriteTransfer
0x180013749  mov     ecx, ebx
0x18001374b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180013750  mov     rcx, [rsp+88h+phSLC]; hSLC
0x180013755  test    rcx, rcx
0x180013758  jz      short loc_180013760
0x18001375a  call    cs:__imp_SLClose
0x180013760  mov     eax, ebx
0x180013762  mov     rcx, [rsp+88h+var_18]
0x180013767  xor     rcx, rsp; StackCookie
0x18001376a  call    __security_check_cookie
0x18001376f  add     rsp, 80h
0x180013776  pop     rbx
0x180013777  retn
```
