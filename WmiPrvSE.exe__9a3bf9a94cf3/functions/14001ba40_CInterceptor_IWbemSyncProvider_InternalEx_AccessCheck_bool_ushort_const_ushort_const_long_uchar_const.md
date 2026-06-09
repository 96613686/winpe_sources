# CInterceptor_IWbemSyncProvider::InternalEx_AccessCheck(bool,ushort const *,ushort const *,long,uchar const *)

- ea: `0x14001ba40`
- end: `0x14001bdab`
- name: `?InternalEx_AccessCheck@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEBG1JPEBE@Z`
- size: `875`
- prototype: `__int64 __usercall@<rax>(CInterceptor_IWbemSyncProvider *__hidden this@<rcx>, bool@<dl>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, int, const unsigned __int8 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001ba10`
- `0x140039160`

## callees

- `0x1400054a0`
- `0x140006c64`
- `0x14001ba40`
- `0x14001bdb4`
- `0x14001c040`
- `0x14001c6d8`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `NCObjAPI!WmiSetAndCommitObject` at `0x14001bad0`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001bc18`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001bad0`
- `NCObjAPI!WmiSetAndCommitObject` at `0x14001bc18`
- `wbemcomn!GetMemLogObject` at `0x14001bcf5`
- `wbemcomn!GetMemLogObject` at `0x14001bd42`
- `wbemcomn!GetMemLogObject` at `0x14001bcf5`
- `wbemcomn!GetMemLogObject` at `0x14001bd42`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001bd05`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001bd4d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001bd05`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14001bd4d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001bc74`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14001bc74`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::InternalEx_AccessCheck(
        CInterceptor_IWbemSyncProvider *this,
        char a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int8 *a6)
{
  unsigned int v10; // esi
  const unsigned __int8 *v11; // r14
  struct _GUID *v12; // r8
  unsigned int v13; // r9d
  struct IUnknown *v14; // rdx
  int v15; // eax
  int v16; // edi
  struct IUnknownVtbl *lpVtbl; // rcx
  struct IUnknown *v18; // rdx
  const struct _GUID *v19; // r8
  unsigned int v20; // r9d
  __int64 result; // rax
  struct IUnknown *v22; // rsi
  struct IServerSecurity *v23; // r13
  CMemoryLog *v24; // rax
  CMemoryLog *MemLogObject; // rax
  int v26; // [rsp+38h] [rbp-51h]
  struct IUnknown **v27; // [rsp+40h] [rbp-49h]
  int v28; // [rsp+60h] [rbp-29h] BYREF
  int v29; // [rsp+64h] [rbp-25h] BYREF
  struct IUnknown *v30; // [rsp+68h] [rbp-21h] BYREF
  struct IServerSecurity *v31; // [rsp+70h] [rbp-19h] BYREF
  struct IUnknown *v32; // [rsp+78h] [rbp-11h] BYREF
  struct IUnknown v33; // [rsp+80h] [rbp-9h] BYREF
  int v34; // [rsp+E0h] [rbp+57h] BYREF

  if ( *((_QWORD *)this + 46) )
  {
    v10 = a5;
    v11 = a6;
    WmiSetAndCommitObject(
      qword_1400613F0,
      1,
      *((_QWORD *)this + 78),
      *(_QWORD *)(*((_QWORD *)this + 75) + 64LL),
      *((_QWORD *)this + 77),
      *((_QWORD *)this + 76),
      *((_QWORD *)this + 79),
      (_DWORD)a3);
    v14 = (struct IUnknown *)*((_QWORD *)this + 46);
    v28 = 0;
    v32 = 0;
    v31 = 0;
    v29 = 0;
    v33.lpVtbl = 0;
    v34 = 0;
    v30 = 0;
    if ( v11 )
      v15 = CInterceptor_IWbemSyncProvider::Begin_Interface_Events(
              this,
              a2,
              v14,
              &IID_IWbemEventProviderSecurity,
              5u,
              &v28,
              &v32,
              &v31,
              &v29,
              (struct IUnknown **)&v33,
              &v34,
              &v30);
    else
      v15 = CInterceptor_IWbemSyncProvider::Begin_Interface(
              this,
              v14,
              v12,
              v13,
              &v28,
              &v32,
              &v31,
              &v29,
              (struct IUnknown **)&v33,
              &v34,
              &v30);
    v16 = v15;
    if ( v15 >= 0 )
    {
      if ( ProviderSubSystem_Globals::s_SharedCounters )
        ++*((_QWORD *)ProviderSubSystem_Globals::s_SharedCounters + 37);
      lpVtbl = v33.lpVtbl;
      ++*((_QWORD *)this + 105);
      v16 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, const unsigned __int8 *))lpVtbl->QueryInterface
             + 3))(
              lpVtbl,
              a3,
              a4,
              v10,
              v11);
      if ( v11 )
      {
        v22 = v30;
        v23 = v31;
        v33.lpVtbl = (struct IUnknownVtbl *)v32;
        CoRevertToSelf();
        if ( v22 )
          ProviderSubSystem_Common_Globals::RevertProxyState(
            (CInterceptor_IWbemSyncProvider *)((char *)this + 440),
            5u,
            v22,
            v34);
        ProviderSubSystem_Common_Globals::EndImpersonation((struct IUnknown *)v33.lpVtbl, v23, v28);
      }
      else
      {
        CInterceptor_IWbemSyncProvider::End_Interface(
          this,
          v18,
          v19,
          v20,
          v28,
          v32,
          v31,
          v26,
          (struct IUnknown *)v27,
          v34,
          v30);
      }
    }
    WmiSetAndCommitObject(
      qword_140061460,
      1,
      *((_QWORD *)this + 78),
      *(_QWORD *)(*((_QWORD *)this + 75) + 64LL),
      *((_QWORD *)this + 77),
      *((_QWORD *)this + 76),
      *((_QWORD *)this + 79),
      (_DWORD)a3);
    result = 2147749890LL;
    if ( v16 != -2147217406 )
    {
      if ( v16 < 0 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v16);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          143,
          WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
          (unsigned int)v16);
      }
      return (unsigned int)v16;
    }
  }
  else
  {
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, -2147217372);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids, 2147749924LL);
    }
    return 2147749924LL;
  }
  return result;
}

```

## disassembly

```asm
0x14001ba40  push    rbp
0x14001ba42  push    rbx
0x14001ba43  push    rsi
0x14001ba44  push    rdi
0x14001ba45  push    r12
0x14001ba47  push    r13
0x14001ba49  push    r14
0x14001ba4b  push    r15
0x14001ba4d  lea     rbp, [rsp-0Fh]
0x14001ba52  sub     rsp, 98h
0x14001ba59  xor     r13d, r13d
0x14001ba5c  mov     r15, r9
0x14001ba5f  mov     r12, r8
0x14001ba62  mov     dil, dl
0x14001ba65  mov     rbx, rcx
0x14001ba68  cmp     [rcx+170h], r13
0x14001ba6f  jz      loc_14001BCF5
0x14001ba75  mov     rax, [rcx+278h]
0x14001ba7c  lea     edx, [r13+1]
0x14001ba80  mov     r9, [rcx+258h]
0x14001ba87  mov     esi, [rbp+47h+arg_20]
0x14001ba8a  mov     r14, [rbp+47h+arg_28]
0x14001ba8e  mov     dword ptr [rsp+0D0h+var_80], esi
0x14001ba92  mov     r9, [r9+40h]
0x14001ba96  mov     [rsp+0D0h+var_88], r14
0x14001ba9b  mov     [rsp+0D0h+var_90], r15
0x14001baa0  mov     [rsp+0D0h+var_98], r8
0x14001baa5  mov     r8, [rcx+270h]
0x14001baac  mov     [rsp+0D0h+var_A0], rax
0x14001bab1  mov     rax, [rcx+260h]
0x14001bab8  mov     [rsp+0D0h+var_A8], rax
0x14001babd  mov     rax, [rcx+268h]
0x14001bac4  mov     rcx, cs:qword_1400613F0
0x14001bacb  mov     [rsp+0D0h+var_B0], rax
0x14001bad0  call    cs:__imp_WmiSetAndCommitObject
0x14001bad6  mov     rdx, [rbx+170h]; struct IUnknown *
0x14001badd  lea     rax, [rbp+47h+var_68]
0x14001bae1  mov     [rbp+47h+var_70], r13d
0x14001bae5  mov     rcx, rbx; this
0x14001bae8  mov     [rbp+47h+var_58], r13
0x14001baec  mov     [rbp+47h+var_60], r13
0x14001baf0  mov     [rbp+47h+var_6C], r13d
0x14001baf4  mov     [rbp+47h+var_50.lpVtbl], r13
0x14001baf8  mov     [rbp+47h+arg_0], r13d
0x14001bafc  mov     [rbp+47h+var_68], r13
0x14001bb00  test    r14, r14
0x14001bb03  jnz     loc_14001BC9B
0x14001bb09  mov     [rsp+0D0h+var_80], rax; struct IUnknown **
0x14001bb0e  lea     rax, [rbp+47h+arg_0]
0x14001bb12  mov     [rsp+0D0h+var_88], rax; int *
0x14001bb17  lea     rax, [rbp+47h+var_50]
0x14001bb1b  mov     [rsp+0D0h+var_90], rax; struct IUnknown *
0x14001bb20  lea     rax, [rbp+47h+var_6C]
0x14001bb24  mov     [rsp+0D0h+var_98], rax; int
0x14001bb29  lea     rax, [rbp+47h+var_60]
0x14001bb2d  mov     [rsp+0D0h+var_A0], rax; struct IServerSecurity **
0x14001bb32  lea     rax, [rbp+47h+var_58]
0x14001bb36  mov     [rsp+0D0h+var_A8], rax; struct IUnknown **
0x14001bb3b  lea     rax, [rbp+47h+var_70]
0x14001bb3f  mov     [rsp+0D0h+var_B0], rax; int *
0x14001bb44  call    ?Begin_Interface@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@2323@Z; CInterceptor_IWbemSyncProvider::Begin_Interface(IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)
0x14001bb49  mov     edi, eax
0x14001bb4b  test    eax, eax
0x14001bb4d  js      short loc_14001BBC3
0x14001bb4f  mov     rax, cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x14001bb56  test    rax, rax
0x14001bb59  jz      short loc_14001BB62
0x14001bb5b  inc     qword ptr [rax+128h]
0x14001bb62  mov     rcx, [rbp+47h+var_50.lpVtbl]
0x14001bb66  mov     r9d, esi
0x14001bb69  inc     qword ptr [rbx+348h]
0x14001bb70  mov     r8, r15
0x14001bb73  mov     rdx, r12
0x14001bb76  mov     [rsp+0D0h+var_B0], r14
0x14001bb7b  mov     rax, [rcx]
0x14001bb7e  mov     rax, [rax+18h]
0x14001bb82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bb87  mov     edi, eax
0x14001bb89  test    r14, r14
0x14001bb8c  jnz     loc_14001BC64
0x14001bb92  mov     rax, [rbp+47h+var_68]
0x14001bb96  mov     rcx, rbx; this
0x14001bb99  mov     [rsp+0D0h+var_80], rax; struct IUnknown *
0x14001bb9e  mov     eax, [rbp+47h+arg_0]
0x14001bba1  mov     dword ptr [rsp+0D0h+var_88], eax; int
0x14001bba5  mov     rax, [rbp+47h+var_60]
0x14001bba9  mov     [rsp+0D0h+var_A0], rax; struct IServerSecurity *
0x14001bbae  mov     rax, [rbp+47h+var_58]
0x14001bbb2  mov     [rsp+0D0h+var_A8], rax; struct IUnknown *
0x14001bbb7  mov     eax, [rbp+47h+var_70]
0x14001bbba  mov     dword ptr [rsp+0D0h+var_B0], eax; int
0x14001bbbe  call    ?End_Interface@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIUnknown@@AEBU_GUID@@KH0PEAUIServerSecurity@@H0H0@Z; CInterceptor_IWbemSyncProvider::End_Interface(IUnknown *,_GUID const &,ulong,int,IUnknown *,IServerSecurity *,int,IUnknown *,int,IUnknown *)
0x14001bbc3  mov     rax, [rbx+278h]
0x14001bbca  mov     edx, 1
0x14001bbcf  mov     r9, [rbx+258h]
0x14001bbd6  mov     r8, [rbx+270h]
0x14001bbdd  mov     rcx, cs:qword_140061460
0x14001bbe4  mov     dword ptr [rsp+0D0h+var_80], esi
0x14001bbe8  mov     r9, [r9+40h]
0x14001bbec  mov     [rsp+0D0h+var_88], r14
0x14001bbf1  mov     [rsp+0D0h+var_90], r15
0x14001bbf6  mov     [rsp+0D0h+var_98], r12
0x14001bbfb  mov     [rsp+0D0h+var_A0], rax
0x14001bc00  mov     rax, [rbx+260h]
0x14001bc07  mov     [rsp+0D0h+var_A8], rax
0x14001bc0c  mov     rax, [rbx+268h]
0x14001bc13  mov     [rsp+0D0h+var_B0], rax
0x14001bc18  call    cs:__imp_WmiSetAndCommitObject
0x14001bc1e  mov     eax, 80041002h
0x14001bc23  cmp     edi, eax
0x14001bc25  jnz     short loc_14001BC3B
0x14001bc27  add     rsp, 98h
0x14001bc2e  pop     r15
0x14001bc30  pop     r14
0x14001bc32  pop     r13
0x14001bc34  pop     r12
0x14001bc36  pop     rdi
0x14001bc37  pop     rsi
0x14001bc38  pop     rbx
0x14001bc39  pop     rbp
0x14001bc3a  retn
0x14001bc3b  test    edi, edi
0x14001bc3d  js      loc_14001BD42
0x14001bc43  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc4a  lea     rax, WPP_GLOBAL_Control
0x14001bc51  cmp     rcx, rax
0x14001bc54  jz      short loc_14001BC60
0x14001bc56  test    byte ptr [rcx+1Ch], 4
0x14001bc5a  jnz     loc_14001BD58
0x14001bc60  mov     eax, edi
0x14001bc62  jmp     short loc_14001BC27
0x14001bc64  mov     rax, [rbp+47h+var_58]
0x14001bc68  mov     rsi, [rbp+47h+var_68]
0x14001bc6c  mov     r13, [rbp+47h+var_60]
0x14001bc70  mov     [rbp+47h+var_50.lpVtbl], rax
0x14001bc74  call    cs:__imp_CoRevertToSelf
0x14001bc7a  test    rsi, rsi
0x14001bc7d  jnz     loc_14001BD25
0x14001bc83  mov     r8d, [rbp+47h+var_70]; int
0x14001bc87  mov     rdx, r13; struct IServerSecurity *
0x14001bc8a  mov     rcx, [rbp+47h+var_50.lpVtbl]; struct IUnknown *
0x14001bc8e  call    ?EndImpersonation@ProviderSubSystem_Common_Globals@@SAJPEAUIUnknown@@PEAUIServerSecurity@@H@Z; ProviderSubSystem_Common_Globals::EndImpersonation(IUnknown *,IServerSecurity *,int)
0x14001bc93  mov     esi, [rbp+47h+arg_20]
0x14001bc96  jmp     loc_14001BBC3
0x14001bc9b  mov     [rsp+0D0h+var_78], rax; struct IUnknown **
0x14001bca0  lea     r9, IID_IWbemEventProviderSecurity; struct _GUID *
0x14001bca7  lea     rax, [rbp+47h+arg_0]
0x14001bcab  mov     r8, rdx; struct IUnknown *
0x14001bcae  mov     [rsp+0D0h+var_80], rax; int *
0x14001bcb3  mov     dl, dil; bool
0x14001bcb6  lea     rax, [rbp+47h+var_50]
0x14001bcba  mov     [rsp+0D0h+var_88], rax; struct IUnknown **
0x14001bcbf  lea     rax, [rbp+47h+var_6C]
0x14001bcc3  mov     [rsp+0D0h+var_90], rax; int *
0x14001bcc8  lea     rax, [rbp+47h+var_60]
0x14001bccc  mov     [rsp+0D0h+var_98], rax; struct IServerSecurity **
0x14001bcd1  lea     rax, [rbp+47h+var_58]
0x14001bcd5  mov     [rsp+0D0h+var_A0], rax; struct IUnknown **
0x14001bcda  lea     rax, [rbp+47h+var_70]
0x14001bcde  mov     [rsp+0D0h+var_A8], rax; int *
0x14001bce3  mov     dword ptr [rsp+0D0h+var_B0], 5; unsigned int
0x14001bceb  call    ?Begin_Interface_Events@CInterceptor_IWbemSyncProvider@@AEAAJ_NPEAUIUnknown@@AEBU_GUID@@KAEAHAEAPEAU2@AEAPEAUIServerSecurity@@3434@Z; CInterceptor_IWbemSyncProvider::Begin_Interface_Events(bool,IUnknown *,_GUID const &,ulong,int &,IUnknown * &,IServerSecurity * &,int &,IUnknown * &,int &,IUnknown * &)
0x14001bcf0  jmp     loc_14001BB49
0x14001bcf5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001bcfb  mov     ebx, 80041024h
0x14001bd00  mov     rcx, rax
0x14001bd03  mov     edx, ebx
0x14001bd05  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001bd0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bd12  lea     rax, WPP_GLOBAL_Control
0x14001bd19  cmp     rcx, rax
0x14001bd1c  jnz     short loc_14001BD7F
0x14001bd1e  mov     eax, ebx
0x14001bd20  jmp     loc_14001BC27
0x14001bd25  mov     r9d, [rbp+47h+arg_0]; int
0x14001bd29  lea     rcx, [rbx+1B8h]; struct ProxyContainer *
0x14001bd30  mov     r8, rsi; struct IUnknown *
0x14001bd33  mov     edx, 5; unsigned int
0x14001bd38  call    ?RevertProxyState@ProviderSubSystem_Common_Globals@@SAJAEAVProxyContainer@@KPEAUIUnknown@@H@Z; ProviderSubSystem_Common_Globals::RevertProxyState(ProxyContainer &,ulong,IUnknown *,int)
0x14001bd3d  jmp     loc_14001BC83
0x14001bd42  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14001bd48  mov     rcx, rax
0x14001bd4b  mov     edx, edi
0x14001bd4d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14001bd53  jmp     loc_14001BC43
0x14001bd58  cmp     byte ptr [rcx+19h], 2
0x14001bd5c  jb      loc_14001BC60
0x14001bd62  mov     rcx, [rcx+10h]
0x14001bd66  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001bd6d  mov     edx, 8Fh
0x14001bd72  mov     r9d, edi
0x14001bd75  call    WPP_SF_d
0x14001bd7a  jmp     loc_14001BC60
0x14001bd7f  test    byte ptr [rcx+1Ch], 4
0x14001bd83  jz      short loc_14001BD1E
0x14001bd85  cmp     byte ptr [rcx+19h], 2
0x14001bd89  jb      short loc_14001BD1E
0x14001bd8b  mov     rcx, [rcx+10h]
0x14001bd8f  lea     r8, WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids
0x14001bd96  mov     edx, 90h
0x14001bd9b  mov     r9d, 80041024h
0x14001bda1  call    WPP_SF_d
0x14001bda6  jmp     loc_14001BD1E
```
