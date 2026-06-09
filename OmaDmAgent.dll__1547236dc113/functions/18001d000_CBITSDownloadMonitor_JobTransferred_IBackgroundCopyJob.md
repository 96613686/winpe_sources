# CBITSDownloadMonitor::JobTransferred(IBackgroundCopyJob *)

- ea: `0x18001d000`
- end: `0x18001d1b8`
- name: `?JobTransferred@CBITSDownloadMonitor@@UEAAJPEAUIBackgroundCopyJob@@@Z`
- size: `440`
- prototype: `int(CBITSDownloadMonitor *__hidden this, struct IBackgroundCopyJob *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002a50`
- `0x18000702c`
- `0x18000a358`
- `0x18000a440`
- `0x18000f8e4`
- `0x180012338`
- `0x18001afb4`
- `0x18001cab8`
- `0x18001d000`
- `0x18001ed00`
- `0x180021010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18001d18d`
- `KERNEL32!SetEvent` at `0x18001d18d`

## pseudocode

```c
__int64 __fastcall CBITSDownloadMonitor::JobTransferred(CBITSDownloadMonitor *this, struct IBackgroundCopyJob *a2)
{
  bool v2; // zf
  LPCWSTR v5; // rcx
  char *v6; // r9
  __int64 v7; // rdx
  int updated; // ebx
  struct IBackgroundCopyJob **v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // r9
  struct JobHelper *JobHelper; // rsi
  unsigned __int16 *v13; // rbx
  _QWORD *v14; // rax
  void **v16; // [rsp+30h] [rbp-78h] BYREF
  __int64 v17; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v19[72]; // [rsp+60h] [rbp-48h] BYREF

  v2 = *((_BYTE *)this + 121) == 0;
  v16 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  v17 = 0;
  if ( !v2 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_8;
    v6 = (char *)this + 128;
    if ( *((_QWORD *)this + 19) >= 8u )
      v6 = *(char **)v6;
    v7 = 14;
LABEL_7:
    WPP_SF_S(*((_QWORD *)v5 + 2), v7, &WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids, v6);
LABEL_8:
    updated = 0;
    goto LABEL_26;
  }
  *((_BYTE *)this + 120) = 1;
  v9 = (struct IBackgroundCopyJob **)SmartPtr<IBackgroundCopyJob>::operator&(&v16);
  if ( (int)ValidateBITSJob(a2, BG_JOB_STATE_TRANSFERRED, v9) < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
      goto LABEL_8;
    v6 = (char *)this + 48;
    if ( *((_QWORD *)this + 9) >= 8u )
      v6 = *(char **)v6;
    v7 = 15;
    goto LABEL_7;
  }
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v10 = (_QWORD *)((char *)this + 48);
    if ( *((_QWORD *)this + 9) >= 8u )
      v10 = (_QWORD *)*v10;
    v11 = (_QWORD *)((char *)this + 128);
    if ( *((_QWORD *)this + 19) >= 8u )
      v11 = (_QWORD *)*v11;
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)&WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids,
      (_DWORD)v11,
      (__int64)v10);
  }
  updated = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *))a2->lpVtbl->Complete)(a2);
  if ( updated >= 0 )
  {
    JobHelper = JobHelper::GetJobHelper();
    if ( *((_BYTE *)this + 80)
      || (v13 = (unsigned __int16 *)std::wstring::wstring(v18, &dword_180022F6C),
          v14 = (_QWORD *)std::wstring::wstring(v19, (char *)this + 128),
          updated = JobHelper::UpdateProgress((__int64)JobHelper, v14, 40, 100, 0, v13),
          updated >= 0) )
    {
      SetEvent(*((HANDLE *)this + 22));
    }
  }
LABEL_26:
  v16 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v17);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18001d000  push    rbx
0x18001d002  push    rsi
0x18001d003  push    rdi
0x18001d004  push    r14
0x18001d006  sub     rsp, 88h
0x18001d00d  cmp     byte ptr [rcx+79h], 0
0x18001d011  lea     r14, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001d018  mov     [rsp+0A8h+var_78], r14
0x18001d01d  mov     rbx, rdx
0x18001d020  mov     rdi, rcx
0x18001d023  mov     [rsp+0A8h+var_70], 0
0x18001d02c  jz      short loc_18001D074
0x18001d02e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d035  lea     rax, WPP_GLOBAL_Control
0x18001d03c  cmp     rcx, rax
0x18001d03f  jz      short loc_18001D06D
0x18001d041  test    byte ptr [rcx+1Ch], 1
0x18001d045  jz      short loc_18001D06D
0x18001d047  lea     r9, [rdi+80h]
0x18001d04e  cmp     qword ptr [r9+18h], 8
0x18001d053  jb      short loc_18001D058
0x18001d055  mov     r9, [r9]
0x18001d058  mov     edx, 0Eh
0x18001d05d  mov     rcx, [rcx+10h]
0x18001d061  lea     r8, WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids
0x18001d068  call    WPP_SF_S
0x18001d06d  xor     ebx, ebx
0x18001d06f  jmp     loc_18001D199
0x18001d074  mov     byte ptr [rcx+78h], 1
0x18001d078  lea     rcx, [rsp+0A8h+var_78]
0x18001d07d  call    ??I?$SmartPtr@UIBackgroundCopyJob@@@@QEAAPEAPEAUIBackgroundCopyJob@@XZ; SmartPtr<IBackgroundCopyJob>::operator&(void)
0x18001d082  mov     r8, rax; struct IBackgroundCopyJob **
0x18001d085  mov     edx, 6; enum BG_JOB_STATE
0x18001d08a  mov     rcx, rbx; struct IBackgroundCopyJob *
0x18001d08d  call    ?ValidateBITSJob@@YAJPEAUIBackgroundCopyJob@@W4BG_JOB_STATE@@PEAPEAU1@@Z; ValidateBITSJob(IBackgroundCopyJob *,BG_JOB_STATE,IBackgroundCopyJob * *)
0x18001d092  test    eax, eax
0x18001d094  jns     short loc_18001D0C4
0x18001d096  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d09d  lea     rax, WPP_GLOBAL_Control
0x18001d0a4  cmp     rcx, rax
0x18001d0a7  jz      short loc_18001D06D
0x18001d0a9  test    byte ptr [rcx+1Ch], 2
0x18001d0ad  jz      short loc_18001D06D
0x18001d0af  lea     r9, [rdi+30h]
0x18001d0b3  cmp     qword ptr [r9+18h], 8
0x18001d0b8  jb      short loc_18001D0BD
0x18001d0ba  mov     r9, [r9]
0x18001d0bd  mov     edx, 0Fh
0x18001d0c2  jmp     short loc_18001D05D
0x18001d0c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0cb  lea     rax, WPP_GLOBAL_Control
0x18001d0d2  cmp     rcx, rax
0x18001d0d5  jz      short loc_18001D116
0x18001d0d7  test    byte ptr [rcx+1Ch], 1
0x18001d0db  jz      short loc_18001D116
0x18001d0dd  lea     rax, [rdi+30h]
0x18001d0e1  cmp     qword ptr [rax+18h], 8
0x18001d0e6  jb      short loc_18001D0EB
0x18001d0e8  mov     rax, [rax]
0x18001d0eb  lea     r9, [rdi+80h]
0x18001d0f2  cmp     qword ptr [r9+18h], 8
0x18001d0f7  jb      short loc_18001D0FC
0x18001d0f9  mov     r9, [r9]
0x18001d0fc  mov     rcx, [rcx+10h]
0x18001d100  lea     r8, WPP_c97e9bd2ae7c3d97c0f7a9732ba19b9f_Traceguids
0x18001d107  mov     edx, 10h
0x18001d10c  mov     [rsp+0A8h+var_88], rax
0x18001d111  call    WPP_SF_SS
0x18001d116  mov     rax, [rbx]
0x18001d119  mov     rcx, rbx
0x18001d11c  mov     rax, [rax+48h]
0x18001d120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d125  mov     ebx, eax
0x18001d127  test    eax, eax
0x18001d129  js      short loc_18001D199
0x18001d12b  call    ?GetJobHelper@JobHelper@@SAPEAV1@XZ; JobHelper::GetJobHelper(void)
0x18001d130  cmp     byte ptr [rdi+50h], 0
0x18001d134  mov     rsi, rax
0x18001d137  jnz     short loc_18001D186
0x18001d139  lea     rdx, dword_180022F6C
0x18001d140  lea     rcx, [rsp+0A8h+var_68]
0x18001d145  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001d14a  lea     rdx, [rdi+80h]
0x18001d151  mov     rbx, rax
0x18001d154  lea     rcx, [rsp+0A8h+var_48]
0x18001d159  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d15e  mov     r9d, 64h ; 'd'
0x18001d164  mov     [rsp+0A8h+var_80], rbx
0x18001d169  mov     rdx, rax
0x18001d16c  mov     dword ptr [rsp+0A8h+var_88], 0
0x18001d174  mov     rcx, rsi
0x18001d177  lea     r8d, [r9-3Ch]
0x18001d17b  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x18001d180  mov     ebx, eax
0x18001d182  test    eax, eax
0x18001d184  js      short loc_18001D199
0x18001d186  mov     rcx, [rdi+0B0h]; hEvent
0x18001d18d  call    cs:__imp_SetEvent
0x18001d194  nop     dword ptr [rax+rax+00h]
0x18001d199  lea     rcx, [rsp+0A8h+var_70]
0x18001d19e  mov     [rsp+0A8h+var_78], r14
0x18001d1a3  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001d1a8  mov     eax, ebx
0x18001d1aa  add     rsp, 88h
0x18001d1b1  pop     r14
0x18001d1b3  pop     rdi
0x18001d1b4  pop     rsi
0x18001d1b5  pop     rbx
0x18001d1b6  retn
```
