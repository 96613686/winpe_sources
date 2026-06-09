# ClusterSpaceControl

- ea: `0x180012920`
- end: `0x180012cc6`
- name: `ClusterSpaceControl`
- size: `934`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x180006290`
- `0x18000f3bc`
- `0x180012920`
- `0x1800175f0`
- `0x18001a5e4`
- `0x180036d44`
- `0x18009304c`
- `0x18010adec`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012b9d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012b9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800129fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800129fe`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800129a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012c7b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800129a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012c7b`
- `RPCRT4!RpcImpersonateClient` at `0x1800129c5`
- `RPCRT4!RpcImpersonateClient` at `0x1800129c5`
- `RPCRT4!RpcRevertToSelf` at `0x180012c83`
- `RPCRT4!RpcRevertToSelf` at `0x180012c83`

## string_xrefs

- `0x1800129f7`: `mispace.dll`

## pseudocode

```c
__int64 __fastcall ClusterSpaceControl(
        __int64 a1,
        void *a2,
        __int64 a3,
        unsigned int a4,
        void *a5,
        unsigned int a6,
        unsigned int *a7)
{
  signed int v7; // ebx
  enum _MI_Result v11; // eax
  int v12; // r14d
  RPC_STATUS v13; // eax
  unsigned __int64 *refreshed; // rax
  __int128 v15; // xmm0
  unsigned int v16; // edx
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // edx
  __int128 v21; // xmm0
  __int64 v22; // rdx
  _OWORD *v23; // rcx
  _OWORD *v24; // rax
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm0
  __int128 v31; // xmm1
  __int128 v32; // xmm1
  __int64 v33; // r9
  __int64 v34; // r8
  __int64 v35; // rdx
  __int128 v36; // xmm0
  _BYTE v38[560]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v39; // [rsp+280h] [rbp+180h] BYREF
  __int64 v40; // [rsp+290h] [rbp+190h]
  GUID ActivityId; // [rsp+298h] [rbp+198h] BYREF

  v7 = 0;
  ActivityId = GUID_NULL;
  LODWORD(v39) = 0;
  v11 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v11 )
  {
    v12 = 0;
    if ( v11 == MI_RESULT_SERVER_IS_SHUTTING_DOWN )
      v7 = -2147023781;
  }
  else
  {
    v12 = 1;
    *a7 = 0;
    if ( a2 )
    {
      if ( !SetThreadToken(0, a2) )
      {
        _status_t::GetLastError((_status_t *)&v39);
        v7 = v39;
LABEL_38:
        SetThreadToken(0, 0);
        goto LABEL_40;
      }
    }
    else
    {
      v13 = RpcImpersonateClient(0);
      v7 = v13;
      if ( v13 > 0 )
        v7 = (unsigned __int16)v13 | 0x80070000;
      LODWORD(v39) = v7;
      if ( v7 < 0 )
        goto LABEL_39;
    }
    if ( a4 < 8 )
      goto LABEL_9;
    g_SpacesModule = GetModuleHandleW(L"mispace.dll");
    if ( !g_SpacesModule )
    {
      _status_t::GetLastError((_status_t *)&v39);
      v7 = v39;
      goto LABEL_37;
    }
    refreshed = (unsigned __int64 *)SuexRefreshClusterSubsystem(&v39, 0);
    v7 = _mm_cvtsi128_si32((__m128i)*refreshed);
    DWORD2(v39) = *((_DWORD *)refreshed + 2);
    if ( v7 >= 0 )
    {
      if ( *(_QWORD *)a3 == 2147549183LL )
      {
        if ( a4 >= 0x48 )
        {
          v15 = *(_OWORD *)(a3 + 32);
          v40 = *(_QWORD *)(a3 + 48);
          v39 = v15;
          ActivityId = *(GUID *)(a3 + 56);
          v16 = *(_DWORD *)(a3 + 12);
          if ( v16 <= a4 && *(_DWORD *)(a3 + 8) >= 0x48u )
          {
            v17 = *(unsigned int *)(a3 + 28);
            if ( (unsigned int)v17 >= *(_DWORD *)(a3 + 8) && (unsigned int)v17 <= v16 )
            {
              v18 = PmcControlDispatch(
                      *(_DWORD *)(a3 + 24),
                      v16 - v17,
                      (void *)(a3 + v17),
                      a6,
                      a5,
                      a7,
                      &v39,
                      &ActivityId);
              goto LABEL_20;
            }
          }
        }
      }
      else
      {
        v40 = 0;
        v39 = 0;
        if ( a4 >= 0x23C )
        {
          v19 = *(_DWORD *)(a3 + 568);
          if ( v19 >= 0x23C && v19 <= a4 )
          {
            v20 = v19 + *(_DWORD *)(a3 + 564);
            if ( v20 >= v19 && v20 <= a4 )
            {
              if ( a4 >= 0x278 && *(_QWORD *)(a3 + 576) == 0x7415150A600D57ACLL && *(_DWORD *)(a3 + 588) >= 0x278u )
              {
                v21 = *(_OWORD *)(a3 + 592);
                v40 = *(_QWORD *)(a3 + 608);
                v39 = v21;
                ActivityId = *(GUID *)(a3 + 616);
              }
              else
              {
                EventActivityIdControl(1u, &ActivityId);
              }
              v22 = 4;
              v23 = v38;
              v24 = (_OWORD *)a3;
              do
              {
                v25 = v24[1];
                *v23 = *v24;
                v26 = v24[2];
                v23[1] = v25;
                v27 = v24[3];
                v23[2] = v26;
                v28 = v24[4];
                v23[3] = v27;
                v29 = v24[5];
                v23[4] = v28;
                v30 = v24[6];
                v23[5] = v29;
                v31 = v24[7];
                v24 += 8;
                v23[6] = v30;
                v23[7] = v31;
                v23 += 8;
                --v22;
              }
              while ( v22 );
              v32 = v24[1];
              v33 = *(unsigned int *)(a3 + 564);
              v34 = a3 + *(unsigned int *)(a3 + 568);
              v35 = *(unsigned int *)(a3 + 560);
              *v23 = *v24;
              v36 = v24[2];
              v23[1] = v32;
              v23[2] = v36;
              v18 = ControlDispatch(v38, v35, v34, v33, a5, a6, a7, &v39, &ActivityId);
LABEL_20:
              v7 = v18;
              if ( v18 > 0 )
                v7 = (unsigned __int16)v18 | 0x80070000;
              goto LABEL_37;
            }
          }
        }
      }
LABEL_9:
      v7 = -2147024809;
    }
  }
LABEL_37:
  if ( a2 )
    goto LABEL_38;
LABEL_39:
  RpcRevertToSelf();
LABEL_40:
  if ( v12 )
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012920  mov     [rsp-8+arg_0], rbx
0x180012925  push    rbp
0x180012926  push    rsi
0x180012927  push    rdi
0x180012928  push    r12
0x18001292a  push    r13
0x18001292c  push    r14
0x18001292e  push    r15
0x180012930  lea     rbp, [rsp-1B0h]
0x180012938  sub     rsp, 2B0h
0x18001293f  mov     rax, cs:__security_cookie
0x180012946  xor     rax, rsp
0x180012949  mov     [rbp+1E0h+var_38], rax
0x180012950  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180012957  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18001295e  xor     ebx, ebx
0x180012960  mov     r13, [rbp+1E0h+arg_20]
0x180012967  mov     esi, r9d
0x18001296a  mov     r12, [rbp+1E0h+arg_30]
0x180012971  mov     rdi, r8
0x180012974  movdqu  xmmword ptr [rbp+1E0h+ActivityId.Data1], xmm0
0x18001297c  mov     r15, rdx
0x18001297f  mov     dword ptr [rbp+1E0h+var_60], ebx
0x180012985  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18001298a  test    eax, eax
0x18001298c  jnz     loc_180012C65
0x180012992  lea     r14d, [rbx+1]
0x180012996  mov     [r12], ebx
0x18001299a  xor     ecx, ecx; BindingHandle
0x18001299c  test    r15, r15
0x18001299f  jz      short loc_1800129C5
0x1800129a1  mov     rdx, r15; Token
0x1800129a4  call    cs:__imp_SetThreadToken
0x1800129aa  test    eax, eax
0x1800129ac  jnz     short loc_1800129E8
0x1800129ae  lea     rcx, [rbp+1E0h+var_60]; this
0x1800129b5  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x1800129ba  mov     ebx, dword ptr [rbp+1E0h+var_60]
0x1800129c0  jmp     loc_180012C77
0x1800129c5  call    cs:__imp_RpcImpersonateClient
0x1800129cb  mov     ebx, eax
0x1800129cd  test    eax, eax
0x1800129cf  jle     short loc_1800129DA
0x1800129d1  movzx   ebx, ax
0x1800129d4  or      ebx, 80070000h
0x1800129da  mov     dword ptr [rbp+1E0h+var_60], ebx
0x1800129e0  test    ebx, ebx
0x1800129e2  js      loc_180012C83
0x1800129e8  cmp     esi, 8
0x1800129eb  jnb     short loc_1800129F7
0x1800129ed  mov     ebx, 80070057h
0x1800129f2  jmp     loc_180012C72
0x1800129f7  lea     rcx, aMispaceDll_0; "mispace.dll"
0x1800129fe  call    cs:__imp_GetModuleHandleW
0x180012a04  mov     cs:?g_SpacesModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_SpacesModule
0x180012a0b  lea     rcx, [rbp+1E0h+var_60]; this
0x180012a12  test    rax, rax
0x180012a15  jnz     short loc_180012A27
0x180012a17  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x180012a1c  mov     ebx, dword ptr [rbp+1E0h+var_60]
0x180012a22  jmp     loc_180012C72
0x180012a27  xor     edx, edx
0x180012a29  call    ?SuexRefreshClusterSubsystem@@YA?AV_status_t@@PEAH@Z; SuexRefreshClusterSubsystem(int *)
0x180012a2e  movsd   xmm0, qword ptr [rax]
0x180012a32  mov     eax, [rax+8]
0x180012a35  movd    ebx, xmm0
0x180012a39  mov     dword ptr [rbp+1E0h+var_60+8], eax
0x180012a3f  test    ebx, ebx
0x180012a41  js      loc_180012C72
0x180012a47  mov     eax, 8000FFFFh
0x180012a4c  cmp     [rdi], rax
0x180012a4f  jnz     loc_180012AF5
0x180012a55  cmp     esi, 48h ; 'H'
0x180012a58  jb      short loc_1800129ED
0x180012a5a  movups  xmm0, xmmword ptr [rdi+20h]
0x180012a5e  mov     rax, [rdi+30h]
0x180012a62  mov     [rbp+1E0h+var_50], rax
0x180012a69  movdqu  [rbp+1E0h+var_60], xmm0
0x180012a71  movups  xmm0, xmmword ptr [rdi+38h]
0x180012a75  movdqu  xmmword ptr [rbp+1E0h+ActivityId.Data1], xmm0
0x180012a7d  mov     edx, [rdi+0Ch]
0x180012a80  cmp     edx, esi
0x180012a82  ja      loc_1800129ED
0x180012a88  cmp     dword ptr [rdi+8], 48h ; 'H'
0x180012a8c  jb      loc_1800129ED
0x180012a92  mov     eax, [rdi+1Ch]
0x180012a95  cmp     eax, [rdi+8]
0x180012a98  jb      loc_1800129ED
0x180012a9e  cmp     eax, edx
0x180012aa0  ja      loc_1800129ED
0x180012aa6  mov     r9d, [rbp+1E0h+arg_28]; unsigned int
0x180012aad  lea     r8, [rdi+rax]; void *
0x180012ab1  mov     ecx, [rdi+18h]; unsigned int
0x180012ab4  sub     edx, eax; unsigned int
0x180012ab6  lea     rax, [rbp+1E0h+ActivityId]
0x180012abd  mov     [rsp+2E0h+var_2A8], rax; struct _GUID *
0x180012ac2  lea     rax, [rbp+1E0h+var_60]
0x180012ac9  mov     [rsp+2E0h+var_2B0], rax; void *
0x180012ace  mov     [rsp+2E0h+var_2B8], r12; unsigned int *
0x180012ad3  mov     [rsp+2E0h+var_2C0], r13; void *
0x180012ad8  call    ?PmcControlDispatch@@YAKKKPEAXK0PEAK0PEAU_GUID@@@Z; PmcControlDispatch(ulong,ulong,void *,ulong,void *,ulong *,void *,_GUID *)
0x180012add  mov     ebx, eax
0x180012adf  test    eax, eax
0x180012ae1  jle     loc_180012C72
0x180012ae7  movzx   ebx, ax
0x180012aea  or      ebx, 80070000h
0x180012af0  jmp     loc_180012C72
0x180012af5  xor     eax, eax
0x180012af7  xorps   xmm0, xmm0
0x180012afa  mov     [rbp+1E0h+var_50], rax
0x180012b01  mov     eax, 23Ch
0x180012b06  movups  [rbp+1E0h+var_60], xmm0
0x180012b0d  cmp     esi, eax
0x180012b0f  jb      loc_1800129ED
0x180012b15  mov     ecx, [rdi+238h]
0x180012b1b  cmp     ecx, eax
0x180012b1d  jb      loc_1800129ED
0x180012b23  cmp     ecx, esi
0x180012b25  ja      loc_1800129ED
0x180012b2b  mov     edx, [rdi+234h]
0x180012b31  add     edx, ecx
0x180012b33  cmp     edx, ecx
0x180012b35  jb      loc_1800129ED
0x180012b3b  cmp     edx, esi
0x180012b3d  ja      loc_1800129ED
0x180012b43  lea     ecx, [rax+3Ch]
0x180012b46  cmp     esi, ecx
0x180012b48  jb      short loc_180012B93
0x180012b4a  mov     rax, 7415150A600D57ACh
0x180012b54  cmp     [rdi+240h], rax
0x180012b5b  jnz     short loc_180012B93
0x180012b5d  cmp     [rdi+24Ch], ecx
0x180012b63  jb      short loc_180012B93
0x180012b65  movups  xmm0, xmmword ptr [rdi+250h]
0x180012b6c  mov     rax, [rdi+260h]
0x180012b73  mov     [rbp+1E0h+var_50], rax
0x180012b7a  movdqu  [rbp+1E0h+var_60], xmm0
0x180012b82  movups  xmm0, xmmword ptr [rdi+268h]
0x180012b89  movdqu  xmmword ptr [rbp+1E0h+ActivityId.Data1], xmm0
0x180012b91  jmp     short loc_180012BA3
0x180012b93  lea     rdx, [rbp+1E0h+ActivityId]; ActivityId
0x180012b9a  mov     ecx, r14d; ControlCode
0x180012b9d  call    cs:__imp_EventActivityIdControl
0x180012ba3  mov     edx, 4
0x180012ba8  lea     rcx, [rsp+2E0h+var_290]
0x180012bad  mov     rax, rdi
0x180012bb0  lea     r8d, [rdx+7Ch]
0x180012bb4  movups  xmm0, xmmword ptr [rax]
0x180012bb7  movups  xmm1, xmmword ptr [rax+10h]
0x180012bbb  movups  xmmword ptr [rcx], xmm0
0x180012bbe  movups  xmm0, xmmword ptr [rax+20h]
0x180012bc2  movups  xmmword ptr [rcx+10h], xmm1
0x180012bc6  movups  xmm1, xmmword ptr [rax+30h]
0x180012bca  movups  xmmword ptr [rcx+20h], xmm0
0x180012bce  movups  xmm0, xmmword ptr [rax+40h]
0x180012bd2  movups  xmmword ptr [rcx+30h], xmm1
0x180012bd6  movups  xmm1, xmmword ptr [rax+50h]
0x180012bda  movups  xmmword ptr [rcx+40h], xmm0
0x180012bde  movups  xmm0, xmmword ptr [rax+60h]
0x180012be2  movups  xmmword ptr [rcx+50h], xmm1
0x180012be6  movups  xmm1, xmmword ptr [rax+70h]
0x180012bea  add     rax, r8
0x180012bed  movups  xmmword ptr [rcx+60h], xmm0
0x180012bf1  movups  xmmword ptr [rcx+70h], xmm1
0x180012bf5  add     rcx, r8
0x180012bf8  sub     rdx, r14
0x180012bfb  jnz     short loc_180012BB4
0x180012bfd  movups  xmm0, xmmword ptr [rax]
0x180012c00  mov     r8d, [rdi+238h]
0x180012c07  movups  xmm1, xmmword ptr [rax+10h]
0x180012c0b  mov     r9d, [rdi+234h]
0x180012c12  add     r8, rdi
0x180012c15  mov     edx, [rdi+230h]
0x180012c1b  movups  xmmword ptr [rcx], xmm0
0x180012c1e  movups  xmm0, xmmword ptr [rax+20h]
0x180012c22  lea     rax, [rbp+1E0h+ActivityId]
0x180012c29  mov     [rsp+2E0h+var_2A0], rax
0x180012c2e  lea     rax, [rbp+1E0h+var_60]
0x180012c35  mov     [rsp+2E0h+var_2A8], rax
0x180012c3a  mov     eax, [rbp+1E0h+arg_28]
0x180012c40  movups  xmmword ptr [rcx+10h], xmm1
0x180012c44  mov     [rsp+2E0h+var_2B0], r12
0x180012c49  movups  xmmword ptr [rcx+20h], xmm0
0x180012c4d  mov     dword ptr [rsp+2E0h+var_2B8], eax
0x180012c51  lea     rcx, [rsp+2E0h+var_290]
0x180012c56  mov     [rsp+2E0h+var_2C0], r13
0x180012c5b  call    ?ControlDispatch@@YAKU_SP_CONTROL_HANDLE@@KPEAXK1KPEAK1PEAU_GUID@@@Z; ControlDispatch(_SP_CONTROL_HANDLE,ulong,void *,ulong,void *,ulong,ulong *,void *,_GUID *)
0x180012c60  jmp     loc_180012ADD
0x180012c65  xor     r14d, r14d
0x180012c68  cmp     eax, 1Ch
0x180012c6b  jnz     short loc_180012C72
0x180012c6d  mov     ebx, 8007045Bh
0x180012c72  test    r15, r15
0x180012c75  jz      short loc_180012C83
0x180012c77  xor     edx, edx; Token
0x180012c79  xor     ecx, ecx; Thread
0x180012c7b  call    cs:__imp_SetThreadToken
0x180012c81  jmp     short loc_180012C89
0x180012c83  call    cs:__imp_RpcRevertToSelf
0x180012c89  test    r14d, r14d
0x180012c8c  jz      short loc_180012C9A
0x180012c8e  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180012c95  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180012c9a  mov     eax, ebx
0x180012c9c  mov     rcx, [rbp+1E0h+var_38]
0x180012ca3  xor     rcx, rsp; StackCookie
0x180012ca6  call    __security_check_cookie
0x180012cab  mov     rbx, [rsp+2E0h+arg_0]
0x180012cb3  add     rsp, 2B0h
0x180012cba  pop     r15
0x180012cbc  pop     r14
0x180012cbe  pop     r13
0x180012cc0  pop     r12
0x180012cc2  pop     rdi
0x180012cc3  pop     rsi
0x180012cc4  pop     rbp
0x180012cc5  retn
```
