# CXvmProxyAudioObjectManager::ActivateAudioEffectsManager(XvmActivateProxyAudioObject *,IProxyMediaNotificationForwarder *,IXvmApiAccessChecker *,IXvmProxyAudioObject * *)

- ea: `0x180097000`
- end: `0x1800974a0`
- name: `?ActivateAudioEffectsManager@CXvmProxyAudioObjectManager@@AEAAJPEAUXvmActivateProxyAudioObject@@PEAUIProxyMediaNotificationForwarder@@PEAUIXvmApiAccessChecker@@PEAPEAUIXvmProxyAudioObject@@@Z`
- size: `1184`
- prototype: `__int64 __fastcall(CXvmProxyAudioObjectManager *__hidden this, struct XvmActivateProxyAudioObject *, struct IProxyMediaNotificationForwarder *, struct IXvmApiAccessChecker *, struct IXvmProxyAudioObject **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180007f00`
- `0x180010a90`
- `0x180087e80`
- `0x180088ce8`
- `0x180096510`
- `0x1800969d8`
- `0x180097000`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800970eb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180097237`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009736a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800970eb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180097237`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009736a`

## string_xrefs

- `0x180097066`: `avcore\published\audiocore\include\crossvmservicecalls.h`
- `0x1800972fd`: `avcore\published\audiocore\include\crossvmservicecalls.h`
- `0x180097081`: `avcore\published\audiocore\include\CrossVmComm.h`
- `0x180097318`: `avcore\published\audiocore\include\CrossVmComm.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXvmProxyAudioObjectManager::ActivateAudioEffectsManager(
        CXvmProxyAudioObjectManager *this,
        struct XvmActivateProxyAudioObject *a2,
        struct IProxyMediaNotificationForwarder *a3,
        struct IXvmApiAccessChecker *a4,
        struct IXvmProxyAudioObject **a5)
{
  __int64 v8; // rdx
  HRESULT v10; // esi
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  _OWORD *v13; // rdi
  _OWORD *v14; // rax
  __int64 v15; // rdx
  int v16; // eax
  int v17; // eax
  _OWORD *v18; // rdi
  _OWORD *v19; // rax
  __int64 v20; // rdx
  int v21; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppvc; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  int ppvd; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v28; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v29; // [rsp+40h] [rbp-C0h] BYREF
  char v30; // [rsp+48h] [rbp-B8h]
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h]
  int v33; // [rsp+5Ch] [rbp-A4h]
  _QWORD v34[256]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+898h] [rbp+798h]

  switch ( *((_DWORD *)a2 + 4) )
  {
    case 'H':
      if ( *((_WORD *)a2 + 273) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x157,
          (unsigned int)"avcore\\published\\audiocore\\include\\crossvmservicecalls.h",
          (const char *)0x80070057LL,
          ppv);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x222,
          (unsigned int)"avcore\\published\\audiocore\\include\\CrossVmComm.h",
          (const char *)0x80070057LL,
          ppvc);
        v8 = 477;
LABEL_4:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"avcore\\audiocore\\client\\audioclient\\xvmproxyaudioobjectmanager.cpp",
          (const char *)0x80070057LL,
          ppva);
        return 2147942487LL;
      }
      v27 = 0;
      v28 = &v27;
      v29 = 0;
      v30 = 1;
      v10 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_de889ace_f1ef_48b9_b599_1a9bf1541cc5, &v29);
      wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<ISimpleAudioVolume,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<ISimpleAudioVolume,wil::err_returncode_policy>>(&v28);
      if ( v10 < 0 )
      {
        v11 = (unsigned int)v10;
        v12 = 480;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"avcore\\audiocore\\client\\audioclient\\xvmproxyaudioobjectmanager.cpp",
          (const char *)v11,
          ppvb);
        wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v27);
        return (unsigned int)v10;
      }
      v13 = (_OWORD *)((char *)a2 + 20);
      v31 = 0;
      v33 = 0;
      memset_0(v34, 0, sizeof(v34));
      v14 = v34;
      v15 = 4;
      do
      {
        *v14 = *v13;
        v14[1] = v13[1];
        v14[2] = v13[2];
        v14[3] = v13[3];
        v14[4] = v13[4];
        v14[5] = v13[5];
        v14[6] = v13[6];
        v14[7] = v13[7];
        v14 += 8;
        v13 += 8;
        --v15;
      }
      while ( v15 );
      *v14 = *v13;
      v32 = 72;
      v16 = (*(__int64 (__fastcall **)(__int64, __int64 *, struct IProxyMediaNotificationForwarder *, struct IXvmApiAccessChecker *))(*(_QWORD *)v27 + 24LL))(
              v27,
              &v31,
              a3,
              a4);
      v10 = v16;
      if ( v16 < 0 )
      {
        v11 = (unsigned int)v16;
        v12 = 482;
        goto LABEL_11;
      }
      goto LABEL_28;
    case 'J':
      v27 = 0;
      v28 = &v27;
      v29 = 0;
      v30 = 1;
      v10 = CoCreateInstance(&stru_1801530E0, 0, 0x17u, &GUID_de889ace_f1ef_48b9_b599_1a9bf1541cc5, &v29);
      wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<ISimpleAudioVolume,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<ISimpleAudioVolume,wil::err_returncode_policy>>(&v28);
      if ( v10 < 0 )
      {
        v11 = (unsigned int)v10;
        v12 = 492;
        goto LABEL_11;
      }
      v31 = 0;
      v33 = 0;
      memset_0(v34, 0, sizeof(v34));
      v34[0] = *(_QWORD *)((char *)a2 + 20);
      v32 = 74;
      v17 = (*(__int64 (__fastcall **)(__int64, __int64 *, struct IProxyMediaNotificationForwarder *, struct IXvmApiAccessChecker *))(*(_QWORD *)v27 + 24LL))(
              v27,
              &v31,
              a3,
              a4);
      v10 = v17;
      if ( v17 < 0 )
      {
        v11 = (unsigned int)v17;
        v12 = 494;
        goto LABEL_11;
      }
      goto LABEL_28;
    case 'I':
      if ( *((_WORD *)a2 + 273) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x171,
          (unsigned int)"avcore\\published\\audiocore\\include\\crossvmservicecalls.h",
          (const char *)0x80070057LL,
          ppv);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x222,
          (unsigned int)"avcore\\published\\audiocore\\include\\CrossVmComm.h",
          (const char *)0x80070057LL,
          ppvd);
        v8 = 501;
        goto LABEL_4;
      }
      v27 = 0;
      v28 = &v27;
      v29 = 0;
      v30 = 1;
      v10 = CoCreateInstance(&stru_1801530D0, 0, 0x17u, &GUID_de889ace_f1ef_48b9_b599_1a9bf1541cc5, &v29);
      wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<ISimpleAudioVolume,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<ISimpleAudioVolume,wil::err_returncode_policy>>(&v28);
      if ( v10 < 0 )
      {
        v11 = (unsigned int)v10;
        v12 = 504;
        goto LABEL_11;
      }
      v18 = (_OWORD *)((char *)a2 + 20);
      v31 = 0;
      v33 = 0;
      memset_0(v34, 0, sizeof(v34));
      v19 = v34;
      v20 = 4;
      do
      {
        *v19 = *v18;
        v19[1] = v18[1];
        v19[2] = v18[2];
        v19[3] = v18[3];
        v19[4] = v18[4];
        v19[5] = v18[5];
        v19[6] = v18[6];
        v19[7] = v18[7];
        v19 += 8;
        v18 += 8;
        --v20;
      }
      while ( v20 );
      *v19 = *v18;
      v32 = 73;
      v21 = (*(__int64 (__fastcall **)(__int64, __int64 *, struct IProxyMediaNotificationForwarder *, struct IXvmApiAccessChecker *))(*(_QWORD *)v27 + 24LL))(
              v27,
              &v31,
              a3,
              a4);
      v10 = v21;
      if ( v21 < 0 )
      {
        v11 = (unsigned int)v21;
        v12 = 506;
        goto LABEL_11;
      }
LABEL_28:
      wil::com_ptr_t<IXvmApiAccessChecker,wil::err_returncode_policy>::copy_to<IXvmApiAccessChecker>(&v27, a5);
      wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v27);
      return 0;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180097000  mov     [rsp-8+arg_0], rbx
0x180097005  mov     [rsp-8+arg_8], rsi
0x18009700a  push    rbp
0x18009700b  push    rdi
0x18009700c  push    r12
0x18009700e  push    r14
0x180097010  push    r15
0x180097012  lea     rbp, [rsp-770h]
0x18009701a  sub     rsp, 870h
0x180097021  mov     rax, cs:__security_cookie
0x180097028  xor     rax, rsp
0x18009702b  mov     [rbp+790h+var_30], rax
0x180097032  mov     r12, r9
0x180097035  mov     r15, r8
0x180097038  mov     rdi, rdx
0x18009703b  mov     r14, [rbp+790h+arg_20]
0x180097042  cmp     dword ptr [rdx+10h], 48h ; 'H'
0x180097046  jnz     loc_1800971F4
0x18009704c  xor     ebx, ebx
0x18009704e  cmp     [rdx+222h], bx
0x180097055  jz      short loc_1800970B4
0x180097057  mov     rcx, [rbp+798h]; this
0x18009705e  mov     ebx, 80070057h
0x180097063  mov     r9d, ebx; char *
0x180097066  lea     r8, aAvcorePublishe; "avcore\\published\\audiocore\\include\\"...
0x18009706d  mov     edx, 157h; void *
0x180097072  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097077  mov     rcx, [rbp+798h]; this
0x18009707e  mov     r9d, ebx; char *
0x180097081  lea     r8, aAvcorePublishe_2; "avcore\\published\\audiocore\\include\\"...
0x180097088  mov     edx, 222h; void *
0x18009708d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097092  mov     edx, 1DDh; void *
0x180097097  lea     r8, aAvcoreAudiocor_39; "avcore\\audiocore\\client\\audioclient"...
0x18009709e  mov     r9d, ebx; char *
0x1800970a1  mov     rcx, [rbp+798h]; this
0x1800970a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800970ad  mov     eax, ebx
0x1800970af  jmp     loc_180097475
0x1800970b4  mov     [rsp+890h+var_860], rbx
0x1800970b9  lea     rax, [rsp+890h+var_860]
0x1800970be  mov     [rsp+890h+var_858], rax
0x1800970c3  mov     [rsp+890h+var_850], rbx
0x1800970c8  mov     [rsp+890h+var_848], 1
0x1800970cd  lea     rax, [rsp+890h+var_850]
0x1800970d2  mov     qword ptr [rsp+890h+ppv], rax; int
0x1800970d7  lea     r9, _GUID_de889ace_f1ef_48b9_b599_1a9bf1541cc5; riid
0x1800970de  xor     edx, edx; pUnkOuter
0x1800970e0  lea     r8d, [rdx+17h]; dwClsContext
0x1800970e4  lea     rcx, rclsid; rclsid
0x1800970eb  call    cs:__imp_CoCreateInstance
0x1800970f1  mov     esi, eax
0x1800970f3  lea     rcx, [rsp+890h+var_858]
0x1800970f8  call    ??1?$out_param_ptr_t@PEAPEAXV?$com_ptr_t@UISimpleAudioVolume@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<ISimpleAudioVolume,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<ISimpleAudioVolume,wil::err_returncode_policy>>(void)
0x1800970fd  test    esi, esi
0x1800970ff  jns     short loc_18009710E
0x180097101  mov     r9d, esi
0x180097104  mov     edx, 1E0h
0x180097109  jmp     loc_1800971BC
0x18009710e  add     rdi, 14h
0x180097112  mov     [rsp+890h+var_840], rbx
0x180097117  mov     [rsp+890h+var_834], ebx
0x18009711b  xor     edx, edx; Val
0x18009711d  mov     r8d, 800h; Size
0x180097123  lea     rcx, [rsp+890h+var_830]; void *
0x180097128  call    memset_0
0x18009712d  lea     rax, [rsp+890h+var_830]
0x180097132  mov     edx, 4
0x180097137  lea     ecx, [rdx+7Ch]
0x18009713a  movups  xmm0, xmmword ptr [rdi]
0x18009713d  movups  xmmword ptr [rax], xmm0
0x180097140  movups  xmm1, xmmword ptr [rdi+10h]
0x180097144  movups  xmmword ptr [rax+10h], xmm1
0x180097148  movups  xmm0, xmmword ptr [rdi+20h]
0x18009714c  movups  xmmword ptr [rax+20h], xmm0
0x180097150  movups  xmm1, xmmword ptr [rdi+30h]
0x180097154  movups  xmmword ptr [rax+30h], xmm1
0x180097158  movups  xmm0, xmmword ptr [rdi+40h]
0x18009715c  movups  xmmword ptr [rax+40h], xmm0
0x180097160  movups  xmm1, xmmword ptr [rdi+50h]
0x180097164  movups  xmmword ptr [rax+50h], xmm1
0x180097168  movups  xmm0, xmmword ptr [rdi+60h]
0x18009716c  movups  xmmword ptr [rax+60h], xmm0
0x180097170  movups  xmm1, xmmword ptr [rdi+70h]
0x180097174  movups  xmmword ptr [rax+70h], xmm1
0x180097178  add     rax, rcx
0x18009717b  add     rdi, rcx
0x18009717e  sub     rdx, 1
0x180097182  jnz     short loc_18009713A
0x180097184  movups  xmm0, xmmword ptr [rdi]
0x180097187  movups  xmmword ptr [rax], xmm0
0x18009718a  mov     [rsp+890h+var_838], 48h ; 'H'
0x180097192  mov     rcx, [rsp+890h+var_860]
0x180097197  mov     rax, [rcx]
0x18009719a  mov     r9, r12
0x18009719d  mov     r8, r15
0x1800971a0  lea     rdx, [rsp+890h+var_840]
0x1800971a5  mov     rax, [rax+18h]
0x1800971a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800971ae  mov     esi, eax
0x1800971b0  test    eax, eax
0x1800971b2  jns     short loc_1800971E1
0x1800971b4  mov     r9d, eax; char *
0x1800971b7  mov     edx, 1E2h; void *
0x1800971bc  lea     r8, aAvcoreAudiocor_39; "avcore\\audiocore\\client\\audioclient"...
0x1800971c3  mov     rcx, [rbp+798h]; this
0x1800971ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800971cf  nop
0x1800971d0  lea     rcx, [rsp+890h+var_860]; void *
0x1800971d5  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800971da  mov     eax, esi
0x1800971dc  jmp     loc_180097475
0x1800971e1  mov     rdx, r14
0x1800971e4  lea     rcx, [rsp+890h+var_860]
0x1800971e9  call    ??$copy_to@UIXvmApiAccessChecker@@@?$com_ptr_t@UIXvmApiAccessChecker@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAUIXvmApiAccessChecker@@@Z; wil::com_ptr_t<IXvmApiAccessChecker,wil::err_returncode_policy>::copy_to<IXvmApiAccessChecker>(IXvmApiAccessChecker * *)
0x1800971ee  nop
0x1800971ef  jmp     loc_180097462
0x1800971f4  cmp     dword ptr [rdx+10h], 4Ah ; 'J'
0x1800971f8  jnz     loc_1800972D9
0x1800971fe  xor     ebx, ebx
0x180097200  mov     [rsp+890h+var_860], rbx
0x180097205  lea     rax, [rsp+890h+var_860]
0x18009720a  mov     [rsp+890h+var_858], rax
0x18009720f  mov     [rsp+890h+var_850], rbx
0x180097214  mov     [rsp+890h+var_848], 1
0x180097219  lea     rax, [rsp+890h+var_850]
0x18009721e  mov     qword ptr [rsp+890h+ppv], rax; int
0x180097223  lea     r9, _GUID_de889ace_f1ef_48b9_b599_1a9bf1541cc5; riid
0x18009722a  xor     edx, edx; pUnkOuter
0x18009722c  lea     r8d, [rbx+17h]; dwClsContext
0x180097230  lea     rcx, stru_1801530E0; rclsid
0x180097237  call    cs:__imp_CoCreateInstance
0x18009723d  mov     esi, eax
0x18009723f  lea     rcx, [rsp+890h+var_858]
0x180097244  call    ??1?$out_param_ptr_t@PEAPEAXV?$com_ptr_t@UISimpleAudioVolume@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<ISimpleAudioVolume,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<ISimpleAudioVolume,wil::err_returncode_policy>>(void)
0x180097249  test    esi, esi
0x18009724b  jns     short loc_180097257
0x18009724d  mov     r9d, esi
0x180097250  mov     edx, 1ECh
0x180097255  jmp     short loc_1800972AD
0x180097257  mov     [rsp+890h+var_840], rbx
0x18009725c  mov     [rsp+890h+var_834], ebx
0x180097260  xor     edx, edx; Val
0x180097262  mov     r8d, 800h; Size
0x180097268  lea     rcx, [rsp+890h+var_830]; void *
0x18009726d  call    memset_0
0x180097272  mov     rax, [rdi+14h]
0x180097276  mov     [rsp+890h+var_830], rax
0x18009727b  mov     [rsp+890h+var_838], 4Ah ; 'J'
0x180097283  mov     rcx, [rsp+890h+var_860]
0x180097288  mov     rax, [rcx]
0x18009728b  mov     r9, r12
0x18009728e  mov     r8, r15
0x180097291  lea     rdx, [rsp+890h+var_840]
0x180097296  mov     rax, [rax+18h]
0x18009729a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009729f  mov     esi, eax
0x1800972a1  test    eax, eax
0x1800972a3  jns     short loc_1800972C6
0x1800972a5  mov     r9d, eax; char *
0x1800972a8  mov     edx, 1EEh; void *
0x1800972ad  lea     r8, aAvcoreAudiocor_39; "avcore\\audiocore\\client\\audioclient"...
0x1800972b4  mov     rcx, [rbp+798h]; this
0x1800972bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800972c0  nop
0x1800972c1  jmp     loc_1800971D0
0x1800972c6  mov     rdx, r14
0x1800972c9  lea     rcx, [rsp+890h+var_860]
0x1800972ce  call    ??$copy_to@UIXvmApiAccessChecker@@@?$com_ptr_t@UIXvmApiAccessChecker@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAUIXvmApiAccessChecker@@@Z; wil::com_ptr_t<IXvmApiAccessChecker,wil::err_returncode_policy>::copy_to<IXvmApiAccessChecker>(IXvmApiAccessChecker * *)
0x1800972d3  nop
0x1800972d4  jmp     loc_180097462
0x1800972d9  cmp     dword ptr [rdx+10h], 49h ; 'I'
0x1800972dd  jnz     loc_180097470
0x1800972e3  xor     ebx, ebx
0x1800972e5  cmp     [rdx+222h], bx
0x1800972ec  jz      short loc_180097333
0x1800972ee  mov     rcx, [rbp+798h]; this
0x1800972f5  mov     ebx, 80070057h
0x1800972fa  mov     r9d, ebx; char *
0x1800972fd  lea     r8, aAvcorePublishe; "avcore\\published\\audiocore\\include\\"...
0x180097304  mov     edx, 171h; void *
0x180097309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009730e  mov     rcx, [rbp+798h]; this
0x180097315  mov     r9d, ebx; char *
0x180097318  lea     r8, aAvcorePublishe_2; "avcore\\published\\audiocore\\include\\"...
0x18009731f  mov     edx, 222h; void *
0x180097324  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097329  mov     edx, 1F5h
0x18009732e  jmp     loc_180097097
0x180097333  mov     [rsp+890h+var_860], rbx
0x180097338  lea     rax, [rsp+890h+var_860]
0x18009733d  mov     [rsp+890h+var_858], rax
0x180097342  mov     [rsp+890h+var_850], rbx
0x180097347  mov     [rsp+890h+var_848], 1
0x18009734c  lea     rax, [rsp+890h+var_850]
0x180097351  mov     qword ptr [rsp+890h+ppv], rax; int
0x180097356  lea     r9, _GUID_de889ace_f1ef_48b9_b599_1a9bf1541cc5; riid
0x18009735d  xor     edx, edx; pUnkOuter
0x18009735f  lea     r8d, [rdx+17h]; dwClsContext
0x180097363  lea     rcx, stru_1801530D0; rclsid
0x18009736a  call    cs:__imp_CoCreateInstance
0x180097370  mov     esi, eax
0x180097372  lea     rcx, [rsp+890h+var_858]
0x180097377  call    ??1?$out_param_ptr_t@PEAPEAXV?$com_ptr_t@UISimpleAudioVolume@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::com_ptr_t<ISimpleAudioVolume,wil::err_returncode_policy>>::~out_param_ptr_t<void * *,wil::com_ptr_t<ISimpleAudioVolume,wil::err_returncode_policy>>(void)
0x18009737c  test    esi, esi
0x18009737e  jns     short loc_18009738D
0x180097380  mov     r9d, esi
0x180097383  mov     edx, 1F8h
0x180097388  jmp     loc_18009743B
0x18009738d  add     rdi, 14h
0x180097391  mov     [rsp+890h+var_840], rbx
0x180097396  mov     [rsp+890h+var_834], ebx
0x18009739a  xor     edx, edx; Val
0x18009739c  mov     r8d, 800h; Size
0x1800973a2  lea     rcx, [rsp+890h+var_830]; void *
0x1800973a7  call    memset_0
0x1800973ac  lea     rax, [rsp+890h+var_830]
0x1800973b1  mov     edx, 4
0x1800973b6  lea     ecx, [rdx+7Ch]
0x1800973b9  movups  xmm0, xmmword ptr [rdi]
0x1800973bc  movups  xmmword ptr [rax], xmm0
0x1800973bf  movups  xmm1, xmmword ptr [rdi+10h]
0x1800973c3  movups  xmmword ptr [rax+10h], xmm1
0x1800973c7  movups  xmm0, xmmword ptr [rdi+20h]
0x1800973cb  movups  xmmword ptr [rax+20h], xmm0
0x1800973cf  movups  xmm1, xmmword ptr [rdi+30h]
0x1800973d3  movups  xmmword ptr [rax+30h], xmm1
0x1800973d7  movups  xmm0, xmmword ptr [rdi+40h]
0x1800973db  movups  xmmword ptr [rax+40h], xmm0
0x1800973df  movups  xmm1, xmmword ptr [rdi+50h]
0x1800973e3  movups  xmmword ptr [rax+50h], xmm1
0x1800973e7  movups  xmm0, xmmword ptr [rdi+60h]
0x1800973eb  movups  xmmword ptr [rax+60h], xmm0
0x1800973ef  movups  xmm1, xmmword ptr [rdi+70h]
0x1800973f3  movups  xmmword ptr [rax+70h], xmm1
0x1800973f7  add     rax, rcx
0x1800973fa  add     rdi, rcx
0x1800973fd  sub     rdx, 1
0x180097401  jnz     short loc_1800973B9
0x180097403  movups  xmm0, xmmword ptr [rdi]
0x180097406  movups  xmmword ptr [rax], xmm0
0x180097409  mov     [rsp+890h+var_838], 49h ; 'I'
0x180097411  mov     rcx, [rsp+890h+var_860]
0x180097416  mov     rax, [rcx]
0x180097419  mov     r9, r12
0x18009741c  mov     r8, r15
0x18009741f  lea     rdx, [rsp+890h+var_840]
0x180097424  mov     rax, [rax+18h]
0x180097428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009742d  mov     esi, eax
0x18009742f  test    eax, eax
0x180097431  jns     short loc_180097454
0x180097433  mov     r9d, eax; char *
0x180097436  mov     edx, 1FAh; void *
0x18009743b  lea     r8, aAvcoreAudiocor_39; "avcore\\audiocore\\client\\audioclient"...
0x180097442  mov     rcx, [rbp+798h]; this
0x180097449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009744e  nop
0x18009744f  jmp     loc_1800971D0
0x180097454  mov     rdx, r14
0x180097457  lea     rcx, [rsp+890h+var_860]
0x18009745c  call    ??$copy_to@UIXvmApiAccessChecker@@@?$com_ptr_t@UIXvmApiAccessChecker@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAUIXvmApiAccessChecker@@@Z; wil::com_ptr_t<IXvmApiAccessChecker,wil::err_returncode_policy>::copy_to<IXvmApiAccessChecker>(IXvmApiAccessChecker * *)
0x180097461  nop
0x180097462  lea     rcx, [rsp+890h+var_860]; void *
0x180097467  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18009746c  xor     eax, eax
0x18009746e  jmp     short loc_180097475
0x180097470  mov     eax, 80070057h
0x180097475  mov     rcx, [rbp+790h+var_30]
0x18009747c  xor     rcx, rsp; StackCookie
0x18009747f  call    __security_check_cookie
0x180097484  lea     r11, [rsp+890h+var_20]
0x18009748c  mov     rbx, [r11+30h]
0x180097490  mov     rsi, [r11+38h]
0x180097494  mov     rsp, r11
0x180097497  pop     r15
0x180097499  pop     r14
0x18009749b  pop     r12
0x18009749d  pop     rdi
0x18009749e  pop     rbp
0x18009749f  retn
```
