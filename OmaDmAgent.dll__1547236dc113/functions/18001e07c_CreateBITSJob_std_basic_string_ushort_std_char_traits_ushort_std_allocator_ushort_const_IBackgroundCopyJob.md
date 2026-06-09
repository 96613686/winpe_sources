# CreateBITSJob(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,IBackgroundCopyJob * *)

- ea: `0x18001e07c`
- end: `0x18001e14e`
- name: `?CreateBITSJob@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIBackgroundCopyJob@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001b05c`

## callees

- `0x18001afb4`
- `0x18001e044`
- `0x18001e07c`
- `0x18001e3a4`
- `0x18001f420`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateBITSJob(wchar_t *String1, _QWORD *a2)
{
  LPVOID *v4; // rax
  int BITSManager; // ebx
  void **v7; // [rsp+30h] [rbp-38h] BYREF
  __int64 v8; // [rsp+38h] [rbp-30h] BYREF
  __int128 v9; // [rsp+40h] [rbp-28h] BYREF

  v9 = 0;
  v8 = 0;
  v7 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  v4 = (LPVOID *)SmartPtr<IBackgroundCopyManager>::operator&(&v7);
  BITSManager = GetBITSManager(String1, v4);
  if ( BITSManager >= 0 )
  {
    BITSManager = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, __int128 *, _QWORD *))(*(_QWORD *)v8 + 24LL))(
                    v8,
                    L"MDMSW Job",
                    0,
                    &v9,
                    a2);
    if ( BITSManager >= 0 )
      BITSManager = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*a2 + 256LL))(*a2, 0, 0, 0);
  }
  v7 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v8);
  return (unsigned int)BITSManager;
}

```

## disassembly

```asm
0x18001e07c  mov     r11, rsp
0x18001e07f  mov     [r11+18h], rbx
0x18001e083  mov     [r11+20h], rsi
0x18001e087  push    rdi
0x18001e088  sub     rsp, 60h
0x18001e08c  mov     rax, cs:__security_cookie
0x18001e093  xor     rax, rsp
0x18001e096  mov     [rsp+68h+var_18], rax
0x18001e09b  mov     rdi, rdx
0x18001e09e  mov     rbx, rcx
0x18001e0a1  xorps   xmm0, xmm0
0x18001e0a4  movups  [rsp+68h+var_28], xmm0
0x18001e0a9  mov     qword ptr [r11-30h], 0
0x18001e0b1  lea     rsi, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001e0b8  mov     [r11-38h], rsi
0x18001e0bc  lea     rcx, [r11-38h]
0x18001e0c0  call    ??I?$SmartPtr@UIBackgroundCopyManager@@@@QEAAPEAPEAUIBackgroundCopyManager@@XZ; SmartPtr<IBackgroundCopyManager>::operator&(void)
0x18001e0c5  mov     rdx, rax; ppv
0x18001e0c8  mov     rcx, rbx; String1
0x18001e0cb  call    GetBITSManager
0x18001e0d0  mov     ebx, eax
0x18001e0d2  test    eax, eax
0x18001e0d4  js      short loc_18001E11D
0x18001e0d6  mov     rcx, [rsp+68h+var_30]
0x18001e0db  mov     rax, [rcx]
0x18001e0de  mov     [rsp+68h+var_48], rdi
0x18001e0e3  lea     r9, [rsp+68h+var_28]
0x18001e0e8  xor     r8d, r8d
0x18001e0eb  lea     rdx, aMdmswJob; "MDMSW Job"
0x18001e0f2  mov     rax, [rax+18h]
0x18001e0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0fb  mov     ebx, eax
0x18001e0fd  test    eax, eax
0x18001e0ff  js      short loc_18001E11D
0x18001e101  mov     rcx, [rdi]
0x18001e104  mov     rax, [rcx]
0x18001e107  xor     r9d, r9d
0x18001e10a  xor     r8d, r8d
0x18001e10d  xor     edx, edx
0x18001e10f  mov     rax, [rax+100h]
0x18001e116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e11b  mov     ebx, eax
0x18001e11d  mov     [rsp+68h+var_38], rsi
0x18001e122  lea     rcx, [rsp+68h+var_30]
0x18001e127  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001e12c  mov     eax, ebx
0x18001e12e  mov     rcx, [rsp+68h+var_18]
0x18001e133  xor     rcx, rsp; StackCookie
0x18001e136  call    __security_check_cookie
0x18001e13b  lea     r11, [rsp+68h+var_8]
0x18001e140  mov     rbx, [r11+20h]
0x18001e144  mov     rsi, [r11+28h]
0x18001e148  mov     rsp, r11
0x18001e14b  pop     rdi
0x18001e14c  retn
```
