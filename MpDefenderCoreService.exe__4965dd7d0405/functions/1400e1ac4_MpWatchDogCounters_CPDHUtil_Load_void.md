# MpWatchDogCounters::CPDHUtil::Load(void)

- ea: `0x1400e1ac4`
- end: `0x1400e1c70`
- name: `?Load@CPDHUtil@MpWatchDogCounters@@QEAA_NXZ`
- size: `428`
- prototype: `bool __fastcall(MpWatchDogCounters::CPDHUtil *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400d85d4`

## callees

- `0x14000dc50`
- `0x14003a5c0`
- `0x14007d210`
- `0x1400e1ac4`
- `0x1400e1d50`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400e1bed`
- `KERNEL32!FreeLibrary` at `0x1400e1c55`
- `KERNEL32!FreeLibrary` at `0x1400e1bed`
- `KERNEL32!FreeLibrary` at `0x1400e1c55`
- `KERNEL32!GetProcAddress` at `0x1400e1b44`
- `KERNEL32!GetProcAddress` at `0x1400e1b59`
- `KERNEL32!GetProcAddress` at `0x1400e1b6f`
- `KERNEL32!GetProcAddress` at `0x1400e1b85`
- `KERNEL32!GetProcAddress` at `0x1400e1b9b`
- `KERNEL32!GetProcAddress` at `0x1400e1bb1`
- `KERNEL32!GetProcAddress` at `0x1400e1b44`
- `KERNEL32!GetProcAddress` at `0x1400e1b59`
- `KERNEL32!GetProcAddress` at `0x1400e1b6f`
- `KERNEL32!GetProcAddress` at `0x1400e1b85`
- `KERNEL32!GetProcAddress` at `0x1400e1b9b`
- `KERNEL32!GetProcAddress` at `0x1400e1bb1`

## string_xrefs

- `0x1400e1aea`: `pdh.dll`
- `0x1400e1b3d`: `PdhOpenQueryW`
- `0x1400e1b64`: `PdhRemoveCounter`

## pseudocode

```c
char __fastcall MpWatchDogCounters::CPDHUtil::Load(MpWatchDogCounters::CPDHUtil *this, __int64 a2, const wchar_t *a3)
{
  int SystemLibrary; // eax
  FARPROC ProcAddress; // rax
  HMODULE v6; // rcx
  FARPROC v7; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  HMODULE v12; // rcx
  FARPROC v13; // rax
  HMODULE v14; // rcx
  FARPROC v15; // rax
  int v16; // r8d
  __int64 v17; // r9
  HMODULE v18; // rcx
  HMODULE hModule; // [rsp+50h] [rbp-18h] BYREF

  hModule = 0;
  SystemLibrary = CommonUtil::UtilLoadSystemLibrary((CommonUtil *)&hModule, (HINSTANCE *)L"pdh.dll", a3);
  if ( SystemLibrary < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        &WPP_d3532b95f198355d9c55676b36a8c4f1_Traceguids,
        (unsigned int)SystemLibrary);
LABEL_17:
    if ( hModule )
      FreeLibrary(hModule);
    return 0;
  }
  ProcAddress = GetProcAddress(hModule, "PdhOpenQueryW");
  v6 = hModule;
  *(_QWORD *)this = ProcAddress;
  v7 = GetProcAddress(v6, "PdhAddEnglishCounterW");
  v8 = hModule;
  *((_QWORD *)this + 1) = v7;
  v9 = GetProcAddress(v8, "PdhRemoveCounter");
  v10 = hModule;
  *((_QWORD *)this + 2) = v9;
  v11 = GetProcAddress(v10, "PdhCloseQuery");
  v12 = hModule;
  *((_QWORD *)this + 3) = v11;
  v13 = GetProcAddress(v12, "PdhCollectQueryData");
  v14 = hModule;
  *((_QWORD *)this + 4) = v13;
  v15 = GetProcAddress(v14, "PdhGetFormattedCounterValue");
  v17 = *(_QWORD *)this;
  *((_QWORD *)this + 5) = v15;
  if ( !v17
    || !*((_QWORD *)this + 1)
    || !*((_QWORD *)this + 2)
    || !*((_QWORD *)this + 3)
    || !*((_QWORD *)this + 4)
    || !v15 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_qqqqqq(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)&WPP_GLOBAL_Control,
        v16,
        v17,
        *((_QWORD *)this + 1),
        *((_QWORD *)this + 2),
        *((_QWORD *)this + 3),
        *((_QWORD *)this + 4),
        (__int64)v15);
    goto LABEL_17;
  }
  v18 = (HMODULE)*((_QWORD *)this + 12);
  if ( v18 )
    FreeLibrary(v18);
  *((_QWORD *)this + 12) = hModule;
  return 1;
}

```

## disassembly

```asm
0x1400e1ac4  push    rbx
0x1400e1ac6  sub     rsp, 60h
0x1400e1aca  mov     rax, cs:__security_cookie
0x1400e1ad1  xor     rax, rsp
0x1400e1ad4  mov     [rsp+68h+var_10], rax
0x1400e1ad9  mov     rbx, rcx
0x1400e1adc  mov     [rsp+68h+hModule], 0
0x1400e1ae5  lea     rcx, [rsp+68h+hModule]; this
0x1400e1aea  lea     rdx, aPdhDll; "pdh.dll"
0x1400e1af1  call    ?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_W@Z; CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,wchar_t const *)
0x1400e1af6  test    eax, eax
0x1400e1af8  jns     short loc_1400E1B38
0x1400e1afa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e1b01  lea     rdx, WPP_GLOBAL_Control
0x1400e1b08  cmp     rcx, rdx
0x1400e1b0b  jz      loc_1400E1C4B
0x1400e1b11  test    byte ptr [rcx+1Ch], 2
0x1400e1b15  jz      loc_1400E1C4B
0x1400e1b1b  mov     rcx, [rcx+10h]
0x1400e1b1f  lea     r8, WPP_d3532b95f198355d9c55676b36a8c4f1_Traceguids
0x1400e1b26  mov     edx, 0Ah
0x1400e1b2b  mov     r9d, eax
0x1400e1b2e  call    WPP_SF_d
0x1400e1b33  jmp     loc_1400E1C4B
0x1400e1b38  mov     rcx, [rsp+68h+hModule]; hModule
0x1400e1b3d  lea     rdx, aPdhopenqueryw; "PdhOpenQueryW"
0x1400e1b44  call    cs:__imp_GetProcAddress
0x1400e1b4a  mov     rcx, [rsp+68h+hModule]; hModule
0x1400e1b4f  lea     rdx, aPdhaddenglishc; "PdhAddEnglishCounterW"
0x1400e1b56  mov     [rbx], rax
0x1400e1b59  call    cs:__imp_GetProcAddress
0x1400e1b5f  mov     rcx, [rsp+68h+hModule]; hModule
0x1400e1b64  lea     rdx, aPdhremovecount; "PdhRemoveCounter"
0x1400e1b6b  mov     [rbx+8], rax
0x1400e1b6f  call    cs:__imp_GetProcAddress
0x1400e1b75  mov     rcx, [rsp+68h+hModule]; hModule
0x1400e1b7a  lea     rdx, aPdhclosequery; "PdhCloseQuery"
0x1400e1b81  mov     [rbx+10h], rax
0x1400e1b85  call    cs:__imp_GetProcAddress
0x1400e1b8b  mov     rcx, [rsp+68h+hModule]; hModule
0x1400e1b90  lea     rdx, aPdhcollectquer; "PdhCollectQueryData"
0x1400e1b97  mov     [rbx+18h], rax
0x1400e1b9b  call    cs:__imp_GetProcAddress
0x1400e1ba1  mov     rcx, [rsp+68h+hModule]; hModule
0x1400e1ba6  lea     rdx, aPdhgetformatte; "PdhGetFormattedCounterValue"
0x1400e1bad  mov     [rbx+20h], rax
0x1400e1bb1  call    cs:__imp_GetProcAddress
0x1400e1bb7  mov     r9, [rbx]
0x1400e1bba  mov     [rbx+28h], rax
0x1400e1bbe  test    r9, r9
0x1400e1bc1  jz      short loc_1400E1C00
0x1400e1bc3  cmp     qword ptr [rbx+8], 0
0x1400e1bc8  jz      short loc_1400E1C00
0x1400e1bca  cmp     qword ptr [rbx+10h], 0
0x1400e1bcf  jz      short loc_1400E1C00
0x1400e1bd1  cmp     qword ptr [rbx+18h], 0
0x1400e1bd6  jz      short loc_1400E1C00
0x1400e1bd8  cmp     qword ptr [rbx+20h], 0
0x1400e1bdd  jz      short loc_1400E1C00
0x1400e1bdf  test    rax, rax
0x1400e1be2  jz      short loc_1400E1C00
0x1400e1be4  mov     rcx, [rbx+60h]; hLibModule
0x1400e1be8  test    rcx, rcx
0x1400e1beb  jz      short loc_1400E1BF3
0x1400e1bed  call    cs:__imp_FreeLibrary
0x1400e1bf3  mov     rax, [rsp+68h+hModule]
0x1400e1bf8  mov     [rbx+60h], rax
0x1400e1bfc  mov     al, 1
0x1400e1bfe  jmp     short loc_1400E1C5D
0x1400e1c00  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e1c07  lea     rdx, WPP_GLOBAL_Control
0x1400e1c0e  cmp     rcx, rdx
0x1400e1c11  jz      short loc_1400E1C4B
0x1400e1c13  test    byte ptr [rcx+1Ch], 2
0x1400e1c17  jz      short loc_1400E1C4B
0x1400e1c19  mov     rcx, [rcx+10h]
0x1400e1c1d  mov     [rsp+68h+var_28], rax
0x1400e1c22  mov     rax, [rbx+20h]
0x1400e1c26  mov     [rsp+68h+var_30], rax
0x1400e1c2b  mov     rax, [rbx+18h]
0x1400e1c2f  mov     [rsp+68h+var_38], rax
0x1400e1c34  mov     rax, [rbx+10h]
0x1400e1c38  mov     [rsp+68h+var_40], rax
0x1400e1c3d  mov     rax, [rbx+8]
0x1400e1c41  mov     [rsp+68h+var_48], rax
0x1400e1c46  call    WPP_SF_qqqqqq
0x1400e1c4b  mov     rcx, [rsp+68h+hModule]; hLibModule
0x1400e1c50  test    rcx, rcx
0x1400e1c53  jz      short loc_1400E1C5B
0x1400e1c55  call    cs:__imp_FreeLibrary
0x1400e1c5b  xor     al, al
0x1400e1c5d  mov     rcx, [rsp+68h+var_10]
0x1400e1c62  xor     rcx, rsp; StackCookie
0x1400e1c65  call    __security_check_cookie
0x1400e1c6a  add     rsp, 60h
0x1400e1c6e  pop     rbx
0x1400e1c6f  retn
```
