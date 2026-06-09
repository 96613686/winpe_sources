# ValidateBITSJob(IBackgroundCopyJob *,BG_JOB_STATE,IBackgroundCopyJob * *)

- ea: `0x18001ed00`
- end: `0x18001ee1c`
- name: `?ValidateBITSJob@@YAJPEAUIBackgroundCopyJob@@W4BG_JOB_STATE@@PEAPEAU1@@Z`
- size: `284`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *, enum BG_JOB_STATE, struct IBackgroundCopyJob **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001cb10`
- `0x18001d000`

## callees

- `0x1800062ac`
- `0x18001afb4`
- `0x18001cab8`
- `0x18001e154`
- `0x18001ed00`
- `0x18001f420`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ValidateBITSJob(struct IBackgroundCopyJob *a1, enum BG_JOB_STATE a2, struct IBackgroundCopyJob **a3)
{
  __int64 v5; // rdx
  int BITSJob; // ebx
  struct IBackgroundCopyJob **v7; // rax
  struct IBackgroundCopyJob *v8; // rcx
  int v10; // [rsp+20h] [rbp-50h] BYREF
  void **v11; // [rsp+28h] [rbp-48h] BYREF
  struct IBackgroundCopyJob *v12; // [rsp+30h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-38h] BYREF
  _WORD v14[8]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v15; // [rsp+58h] [rbp-18h]
  __int64 v16; // [rsp+60h] [rbp-10h]

  Uuid = 0;
  v12 = 0;
  v11 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  v10 = 0;
  v16 = 7;
  v15 = 0;
  v14[0] = 0;
  BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, UUID *))a1->lpVtbl->GetId)(a1, &Uuid);
  if ( BITSJob >= 0 )
  {
    v7 = (struct IBackgroundCopyJob **)SmartPtr<IBackgroundCopyJob>::operator&(&v11);
    BITSJob = FindBITSJob(&Uuid, v7);
    if ( BITSJob >= 0 )
    {
      BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, int *))v12->lpVtbl->GetState)(v12, &v10);
      if ( BITSJob >= 0 )
      {
        if ( v10 == a2 )
        {
          if ( a3 )
          {
            v8 = v12;
            *a3 = v12;
            if ( v8 )
              ((void (__fastcall *)(struct IBackgroundCopyJob *))v8->lpVtbl->AddRef)(v8);
            BITSJob = 0;
          }
          else
          {
            BITSJob = -2147467261;
          }
        }
        else
        {
          BITSJob = -2147418113;
        }
      }
    }
  }
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(v14, v5, 0);
  v11 = &SmartPtr<IBITSDownloadMonitor>::`vftable';
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)&v12);
  return (unsigned int)BITSJob;
}

```

## disassembly

```asm
0x18001ed00  mov     [rsp-18h+arg_8], rbx
0x18001ed05  mov     [rsp-18h+arg_18], rsi
0x18001ed0a  push    rbp
0x18001ed0b  push    rdi
0x18001ed0c  push    r15
0x18001ed0e  mov     rbp, rsp
0x18001ed11  sub     rsp, 70h
0x18001ed15  mov     rax, cs:__security_cookie
0x18001ed1c  xor     rax, rsp
0x18001ed1f  mov     [rbp+var_8], rax
0x18001ed23  mov     rdi, r8
0x18001ed26  mov     esi, edx
0x18001ed28  xorps   xmm0, xmm0
0x18001ed2b  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18001ed2f  mov     [rbp+var_40], 0
0x18001ed37  lea     r15, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001ed3e  mov     [rbp+var_48], r15
0x18001ed42  mov     [rbp+var_50], 0
0x18001ed49  mov     [rbp+var_10], 7
0x18001ed51  mov     [rbp+var_18], 0
0x18001ed59  xor     eax, eax
0x18001ed5b  mov     [rbp+var_28], ax
0x18001ed5f  mov     rax, [rcx]
0x18001ed62  lea     rdx, [rbp+Uuid]
0x18001ed66  mov     rax, [rax+50h]
0x18001ed6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed6f  mov     ebx, eax
0x18001ed71  test    eax, eax
0x18001ed73  js      short loc_18001EDDC
0x18001ed75  lea     rcx, [rbp+var_48]
0x18001ed79  call    ??I?$SmartPtr@UIBackgroundCopyJob@@@@QEAAPEAPEAUIBackgroundCopyJob@@XZ; SmartPtr<IBackgroundCopyJob>::operator&(void)
0x18001ed7e  mov     rdx, rax; struct IBackgroundCopyJob **
0x18001ed81  lea     rcx, [rbp+Uuid]; Uuid
0x18001ed85  call    ?FindBITSJob@@YAJAEBU_GUID@@PEAPEAUIBackgroundCopyJob@@@Z; FindBITSJob(_GUID const &,IBackgroundCopyJob * *)
0x18001ed8a  mov     ebx, eax
0x18001ed8c  test    eax, eax
0x18001ed8e  js      short loc_18001EDDC
0x18001ed90  mov     rcx, [rbp+var_40]
0x18001ed94  mov     rax, [rcx]
0x18001ed97  lea     rdx, [rbp+var_50]
0x18001ed9b  mov     rax, [rax+70h]
0x18001ed9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eda4  mov     ebx, eax
0x18001eda6  test    eax, eax
0x18001eda8  js      short loc_18001EDDC
0x18001edaa  cmp     [rbp+var_50], esi
0x18001edad  jz      short loc_18001EDB6
0x18001edaf  mov     ebx, 8000FFFFh
0x18001edb4  jmp     short loc_18001EDDC
0x18001edb6  test    rdi, rdi
0x18001edb9  jnz     short loc_18001EDC2
0x18001edbb  mov     ebx, 80004003h
0x18001edc0  jmp     short loc_18001EDDC
0x18001edc2  mov     rcx, [rbp+var_40]
0x18001edc6  mov     [rdi], rcx
0x18001edc9  test    rcx, rcx
0x18001edcc  jz      short loc_18001EDDA
0x18001edce  mov     rax, [rcx]
0x18001edd1  mov     rax, [rax+8]
0x18001edd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edda  xor     ebx, ebx
0x18001eddc  xor     r8d, r8d
0x18001eddf  mov     dl, 1
0x18001ede1  lea     rcx, [rbp+var_28]
0x18001ede5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001edea  nop
0x18001edeb  mov     [rbp+var_48], r15
0x18001edef  lea     rcx, [rbp+var_40]
0x18001edf3  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001edf8  mov     eax, ebx
0x18001edfa  mov     rcx, [rbp+var_8]
0x18001edfe  xor     rcx, rsp; StackCookie
0x18001ee01  call    __security_check_cookie
0x18001ee06  lea     r11, [rsp+70h+var_s0]
0x18001ee0b  mov     rbx, [r11+28h]
0x18001ee0f  mov     rsi, [r11+38h]
0x18001ee13  mov     rsp, r11
0x18001ee16  pop     r15
0x18001ee18  pop     rdi
0x18001ee19  pop     rbp
0x18001ee1a  retn
```
