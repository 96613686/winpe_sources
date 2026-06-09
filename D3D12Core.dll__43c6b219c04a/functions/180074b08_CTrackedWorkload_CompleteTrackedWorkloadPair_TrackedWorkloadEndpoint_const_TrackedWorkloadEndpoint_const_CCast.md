# CTrackedWorkload::CompleteTrackedWorkloadPair(TrackedWorkloadEndpoint const *,TrackedWorkloadEndpoint const *,CCastableCommandQueue *)

- ea: `0x180074b08`
- end: `0x180074cdb`
- name: `?CompleteTrackedWorkloadPair@CTrackedWorkload@@QEAAJPEBUTrackedWorkloadEndpoint@@0PEAVCCastableCommandQueue@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(CTrackedWorkload *__hidden this, const struct TrackedWorkloadEndpoint *, const struct TrackedWorkloadEndpoint *, struct CCastableCommandQueue *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000b2a0`

## callees

- `0x180005b90`
- `0x180007220`
- `0x180007f20`
- `0x18000ac4c`
- `0x180074b08`
- `0x18007ac20`
- `0x1800bb480`
- `0x1800bc094`
- `0x18012745c`
- `0x180262020`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180074cb2`
- `msvcp_win!_Mtx_unlock` at `0x180074cb2`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTUpdateTrackedWorkload` at `0x180074c95`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTrackedWorkload::CompleteTrackedWorkloadPair(
        CTrackedWorkload *this,
        const struct TrackedWorkloadEndpoint *a2,
        const struct TrackedWorkloadEndpoint *a3,
        struct CCastableCommandQueue *a4)
{
  struct _Mtx_internal_imp_t *v8; // r15
  CCastableCommandQueue *v9; // rcx
  int ClockCalibration; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // eax
  unsigned __int64 v15; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v16[3]; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD v17[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h]
  int v19; // [rsp+50h] [rbp-B0h]
  int v20; // [rsp+54h] [rbp-ACh]
  BOOL v21; // [rsp+58h] [rbp-A8h]
  BOOL v22; // [rsp+5Ch] [rbp-A4h]
  __int64 v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+68h] [rbp-98h]
  unsigned __int64 CompletedValue; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  unsigned __int64 v27; // [rsp+80h] [rbp-80h]
  unsigned __int64 v28; // [rsp+88h] [rbp-78h]

  v8 = (CTrackedWorkload *)((char *)this + 264);
  v16[1] = (unsigned __int64)this + 264;
  std::_Mutex_base::lock((CTrackedWorkload *)((char *)this + 264));
  memset_0(v17, 0, 0x258u);
  v9 = (CCastableCommandQueue *)*((_QWORD *)this + 31);
  if ( a4 == v9 )
  {
    if ( *((_QWORD *)this + 44)
      || (ClockCalibration = CCastableCommandQueue::GetTimestampFrequency(v9, (unsigned __int64 *)this + 44),
          ClockCalibration >= 0) )
    {
      v15 = 0;
      v16[0] = 0;
      ClockCalibration = CCastableCommandQueue::GetClockCalibration(*((CCastableCommandQueue **)this + 31), &v15, v16);
      if ( ClockCalibration >= 0 )
      {
        v17[1] = *((_DWORD *)this + 54);
        if ( *(_DWORD *)a3 == 3 )
        {
          if ( *((_DWORD *)this + 51) >= 2u )
          {
            ClockCalibration = -2147418113;
            goto LABEL_11;
          }
          v18 = *((_QWORD *)a3 + 2);
        }
        v17[0] = 600;
        v19 = *((_DWORD *)a2 + 1);
        v21 = *(_DWORD *)a2 == 2;
        v20 = *((_DWORD *)a3 + 1);
        v22 = *(_DWORD *)a3 == 4;
        v23 = *((_QWORD *)a2 + 1);
        v24 = *((unsigned int *)this + 64);
        CompletedValue = CFence::GetCompletedValue(*((CFence **)this + 30));
        v26 = *((_QWORD *)this + 44);
        v27 = v15;
        v28 = v16[0];
        v13 = CallAndLogImpl<long (*)(_D3DKMT_UPDATETRACKEDWORKLOAD *),_D3DKMT_UPDATETRACKEDWORKLOAD *>(
                D3DKMTUpdateTrackedWorkload,
                v11,
                v12,
                v17);
        ClockCalibration = NDXGI::CUMDAdapter::NTStatusToHResult(v13, 1);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 19) + 776LL) + 32LL))(
      *(_QWORD *)(*((_QWORD *)this + 19) + 776LL),
      1211,
      0);
    ClockCalibration = -2147024809;
  }
LABEL_11:
  _Mtx_unlock(v8);
  return (unsigned int)ClockCalibration;
}

```

## disassembly

```asm
0x180074b08  push    rbp
0x180074b0a  push    rbx
0x180074b0b  push    rsi
0x180074b0c  push    rdi
0x180074b0d  push    r13
0x180074b0f  push    r14
0x180074b11  push    r15
0x180074b13  lea     rbp, [rsp-1B0h]
0x180074b1b  sub     rsp, 2B0h
0x180074b22  mov     rax, cs:__security_cookie
0x180074b29  xor     rax, rsp
0x180074b2c  mov     [rbp+1E0h+var_40], rax
0x180074b33  mov     rbx, r9
0x180074b36  mov     rsi, r8
0x180074b39  mov     r13, rdx
0x180074b3c  mov     rdi, rcx
0x180074b3f  lea     r15, [rcx+108h]
0x180074b46  mov     [rsp+2E0h+var_2B0], r15
0x180074b4b  mov     rcx, r15; this
0x180074b4e  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180074b53  nop
0x180074b54  xor     edx, edx; Val
0x180074b56  mov     r8d, 258h; Size
0x180074b5c  lea     rcx, [rsp+2E0h+var_2A0]; void *
0x180074b61  call    memset_0
0x180074b66  mov     rcx, [rdi+0F8h]; this
0x180074b6d  cmp     rbx, rcx
0x180074b70  jz      short loc_180074B9E
0x180074b72  mov     rax, [rdi+98h]
0x180074b79  mov     rcx, [rax+308h]
0x180074b80  mov     rax, [rcx]
0x180074b83  xor     r8d, r8d
0x180074b86  mov     edx, 4BBh
0x180074b8b  mov     rax, [rax+20h]
0x180074b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074b94  mov     ebx, 80070057h
0x180074b99  jmp     loc_180074CAF
0x180074b9e  lea     r14, [rdi+160h]
0x180074ba5  cmp     qword ptr [r14], 0
0x180074ba9  jnz     short loc_180074BBD
0x180074bab  mov     rdx, r14; unsigned __int64 *
0x180074bae  call    ?GetTimestampFrequency@CCastableCommandQueue@@UEAAJPEA_K@Z; CCastableCommandQueue::GetTimestampFrequency(unsigned __int64 *)
0x180074bb3  mov     ebx, eax
0x180074bb5  test    eax, eax
0x180074bb7  js      loc_180074CAF
0x180074bbd  mov     [rsp+2E0h+var_2C0], 0
0x180074bc6  mov     [rsp+2E0h+var_2B8], 0
0x180074bcf  lea     r8, [rsp+2E0h+var_2B8]; unsigned __int64 *
0x180074bd4  lea     rdx, [rsp+2E0h+var_2C0]; unsigned __int64 *
0x180074bd9  mov     rcx, [rdi+0F8h]; this
0x180074be0  call    ?GetClockCalibration@CCastableCommandQueue@@UEAAJPEA_K0@Z; CCastableCommandQueue::GetClockCalibration(unsigned __int64 *,unsigned __int64 *)
0x180074be5  mov     ebx, eax
0x180074be7  test    eax, eax
0x180074be9  js      loc_180074CAF
0x180074bef  mov     eax, [rdi+0D8h]
0x180074bf5  mov     [rsp+2E0h+var_29C], eax
0x180074bf9  cmp     dword ptr [rsi], 3
0x180074bfc  jnz     short loc_180074C20
0x180074bfe  mov     ecx, [rdi+0CCh]
0x180074c04  test    ecx, ecx
0x180074c06  jz      short loc_180074C17
0x180074c08  cmp     ecx, 1
0x180074c0b  jz      short loc_180074C17
0x180074c0d  mov     ebx, 8000FFFFh
0x180074c12  jmp     loc_180074CAF
0x180074c17  mov     rax, [rsi+10h]
0x180074c1b  mov     [rsp+2E0h+var_298], rax
0x180074c20  mov     [rsp+2E0h+var_2A0], 258h
0x180074c28  mov     eax, [r13+4]
0x180074c2c  mov     [rsp+2E0h+var_290], eax
0x180074c30  xor     eax, eax
0x180074c32  cmp     dword ptr [r13+0], 2
0x180074c37  setz    al
0x180074c3a  mov     [rsp+2E0h+var_288], eax
0x180074c3e  mov     eax, [rsi+4]
0x180074c41  mov     [rsp+2E0h+var_28C], eax
0x180074c45  xor     eax, eax
0x180074c47  cmp     dword ptr [rsi], 4
0x180074c4a  setz    al
0x180074c4d  mov     [rsp+2E0h+var_284], eax
0x180074c51  mov     rax, [r13+8]
0x180074c55  mov     [rsp+2E0h+var_280], rax
0x180074c5a  mov     eax, [rdi+100h]
0x180074c60  mov     [rsp+2E0h+var_278], rax
0x180074c65  mov     rcx, [rdi+0F0h]; this
0x180074c6c  call    ?GetCompletedValue@CFence@@UEAA_KXZ; CFence::GetCompletedValue(void)
0x180074c71  mov     [rsp+2E0h+var_270], rax
0x180074c76  mov     rax, [r14]
0x180074c79  mov     [rsp+2E0h+var_268], rax
0x180074c7e  mov     rax, [rsp+2E0h+var_2C0]
0x180074c83  mov     [rbp+1E0h+var_260], rax
0x180074c87  mov     rax, [rsp+2E0h+var_2B8]
0x180074c8c  mov     [rbp+1E0h+var_258], rax
0x180074c90  lea     r9, [rsp+2E0h+var_2A0]
0x180074c95  mov     rcx, cs:__imp_D3DKMTUpdateTrackedWorkload
0x180074c9c  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_UPDATETRACKEDWORKLOAD@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_UPDATETRACKEDWORKLOAD@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(_D3DKMT_UPDATETRACKEDWORKLOAD *),_D3DKMT_UPDATETRACKEDWORKLOAD *>(long (*)(_D3DKMT_UPDATETRACKEDWORKLOAD *),char const *,RecordStatusFilterResult (*)(long),_D3DKMT_UPDATETRACKEDWORKLOAD *)
0x180074ca1  mov     edx, 1
0x180074ca6  mov     ecx, eax
0x180074ca8  call    ?NTStatusToHResult@CUMDAdapter@NDXGI@@SAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CUMDAdapter::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x180074cad  mov     ebx, eax
0x180074caf  mov     rcx, r15; _Mtx_t
0x180074cb2  call    cs:__imp__Mtx_unlock
0x180074cb8  mov     eax, ebx
0x180074cba  mov     rcx, [rbp+1E0h+var_40]
0x180074cc1  xor     rcx, rsp; StackCookie
0x180074cc4  call    __security_check_cookie
0x180074cc9  add     rsp, 2B0h
0x180074cd0  pop     r15
0x180074cd2  pop     r14
0x180074cd4  pop     r13
0x180074cd6  pop     rdi
0x180074cd7  pop     rsi
0x180074cd8  pop     rbx
0x180074cd9  pop     rbp
0x180074cda  retn
```
