# Broker::_SessionInfo::_SessionInfo(void *,bool,unsigned __int64,ulong)

- ea: `0x18001305c`
- end: `0x1800131a8`
- name: `??0_SessionInfo@Broker@@QEAA@PEAX_N_KK@Z`
- size: `332`
- prototype: `Broker::_SessionInfo *__fastcall(Broker::_SessionInfo *this, void *, char, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012b8c`

## callees

- `0x1800076a0`
- `0x18001305c`
- `0x1800131b0`
- `0x18001cf74`
- `0x18001d39c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800130aa`
- `ntdll!RtlCopySid` at `0x1800130aa`
- `ntdll!RtlFreeSid` at `0x1800130b0`
- `ntdll!RtlLengthSid` at `0x180013090`
- `ntdll!RtlLengthSid` at `0x180013090`

## pseudocode

```c
Broker::_SessionInfo *__fastcall Broker::_SessionInfo::_SessionInfo(
        Broker::_SessionInfo *this,
        void *a2,
        char a3,
        __int64 a4,
        unsigned int a5)
{
  ULONG v9; // ebx
  void *v10; // rdi
  void *v11; // r9
  __int64 v12; // rcx
  struct _WNF_STATE_NAME *v13; // rdx
  std::_Ref_count_base *v14; // rcx
  struct _WNF_STATE_NAME *v15; // rdx
  void *v16; // r9
  struct _WNF_STATE_NAME *v17; // rdx
  void *v18; // r9
  struct _WNF_STATE_NAME *v19; // rdx
  void *v20; // r9
  _QWORD v22[3]; // [rsp+30h] [rbp-48h] BYREF
  char v23; // [rsp+48h] [rbp-30h]
  _DWORD *v24; // [rsp+80h] [rbp+8h]

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  v9 = RtlLengthSid(a2);
  v10 = operator new[](v9);
  RtlCopySid(v9, v10, a2);
  v22[0] = RtlFreeSid;
  v22[1] = v10;
  v22[2] = v22;
  v23 = 1;
  v24 = operator new(0x20u);
  v12 = v22[0];
  *(_OWORD *)v24 = 0;
  v24[2] = 1;
  v24[3] = 1;
  v13 = (struct _WNF_STATE_NAME *)&std::_Ref_count_resource<void *,void * (*)(void *)>::`vftable';
  *(_QWORD *)v24 = &std::_Ref_count_resource<void *,void * (*)(void *)>::`vftable';
  *((_QWORD *)v24 + 2) = v12;
  *((_QWORD *)v24 + 3) = v10;
  *(_QWORD *)this = v10;
  v14 = (std::_Ref_count_base *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = v24;
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  *((_BYTE *)this + 16) = a3;
  *(_WORD *)((char *)this + 17) = 256;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = a5;
  *((_QWORD *)this + 6) = a4;
  if ( (int)Broker::CreateTemporaryWnfStateName((Broker::_SessionInfo *)((char *)this + 56), v13, a2, v11) < 0 )
    *((_QWORD *)this + 7) = 0;
  if ( (int)Broker::CreateTemporaryWnfStateName((Broker::_SessionInfo *)((char *)this + 64), v15, a2, v16) < 0 )
    *((_QWORD *)this + 8) = 0;
  if ( (int)Broker::CreateTemporaryWnfStateName((Broker::_SessionInfo *)((char *)this + 72), v17, a2, v18) < 0 )
    *((_QWORD *)this + 9) = 0;
  if ( (int)Broker::CreateTemporaryWnfStateName((Broker::_SessionInfo *)((char *)this + 80), v19, a2, v20) < 0 )
    *((_QWORD *)this + 10) = 0;
  return this;
}

```

## disassembly

```asm
0x18001305c  mov     [rsp+arg_8], rbx
0x180013061  mov     [rsp+arg_10], rbp
0x180013066  mov     [rsp+arg_0], rcx
0x18001306b  push    rsi
0x18001306c  push    rdi
0x18001306d  push    r12
0x18001306f  push    r14
0x180013071  push    r15
0x180013073  sub     rsp, 50h
0x180013077  mov     r14, r9
0x18001307a  mov     r15b, r8b
0x18001307d  mov     rbp, rdx
0x180013080  mov     rsi, rcx
0x180013083  xor     r12d, r12d
0x180013086  mov     [rcx], r12
0x180013089  mov     [rcx+8], r12
0x18001308d  mov     rcx, rdx; Sid
0x180013090  call    cs:__imp_RtlLengthSid
0x180013096  mov     ebx, eax
0x180013098  mov     ecx, eax; unsigned __int64
0x18001309a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001309f  mov     rdi, rax
0x1800130a2  mov     r8, rbp; SourceSid
0x1800130a5  mov     rdx, rax; DestinationSid
0x1800130a8  mov     ecx, ebx; DestinationSidLength
0x1800130aa  call    cs:__imp_RtlCopySid
0x1800130b0  mov     rcx, cs:__imp_RtlFreeSid
0x1800130b7  mov     [rsp+78h+var_48], rcx
0x1800130bc  mov     [rsp+78h+var_40], rdi
0x1800130c1  lea     rax, [rsp+78h+var_48]
0x1800130c6  mov     [rsp+78h+var_38], rax
0x1800130cb  lea     ebx, [r12+1]
0x1800130d0  mov     [rsp+78h+var_30], bl
0x1800130d4  lea     ecx, [rbx+1Fh]; Size
0x1800130d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800130dc  mov     [rsp+78h+arg_0], rax
0x1800130e4  mov     rcx, [rsp+78h+var_48]
0x1800130e9  xorps   xmm0, xmm0
0x1800130ec  movups  xmmword ptr [rax], xmm0
0x1800130ef  mov     [rax+8], ebx
0x1800130f2  mov     [rax+0Ch], ebx
0x1800130f5  lea     rdx, ??_7?$_Ref_count_resource@PEAXP6APEAXPEAX@Z@std@@6B@; const std::_Ref_count_resource<void *,void * (*)(void *)>::`vftable'
0x1800130fc  mov     [rax], rdx
0x1800130ff  mov     [rax+10h], rcx
0x180013103  mov     [rax+18h], rdi
0x180013107  mov     [rsi], rdi
0x18001310a  mov     rcx, [rsi+8]; this
0x18001310e  mov     [rsi+8], rax
0x180013112  test    rcx, rcx
0x180013115  jz      short loc_18001311C
0x180013117  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001311c  mov     [rsi+10h], r15b
0x180013120  mov     word ptr [rsi+11h], 100h
0x180013126  mov     [rsi+18h], r12
0x18001312a  mov     [rsi+20h], r12
0x18001312e  mov     eax, [rsp+78h+arg_20]
0x180013135  mov     [rsi+28h], eax
0x180013138  mov     [rsi+30h], r14
0x18001313c  mov     r8, rbp; unsigned int
0x18001313f  lea     rcx, [rsi+38h]; this
0x180013143  call    ?CreateTemporaryWnfStateName@Broker@@YAJPEAU_WNF_STATE_NAME@@IPEAX1K@Z; Broker::CreateTemporaryWnfStateName(_WNF_STATE_NAME *,uint,void *,void *,ulong)
0x180013148  test    eax, eax
0x18001314a  jns     short loc_180013150
0x18001314c  mov     [rsi+38h], r12
0x180013150  mov     r8, rbp; unsigned int
0x180013153  lea     rcx, [rsi+40h]; this
0x180013157  call    ?CreateTemporaryWnfStateName@Broker@@YAJPEAU_WNF_STATE_NAME@@IPEAX1K@Z; Broker::CreateTemporaryWnfStateName(_WNF_STATE_NAME *,uint,void *,void *,ulong)
0x18001315c  test    eax, eax
0x18001315e  jns     short loc_180013164
0x180013160  mov     [rsi+40h], r12
0x180013164  mov     r8, rbp; unsigned int
0x180013167  lea     rcx, [rsi+48h]; this
0x18001316b  call    ?CreateTemporaryWnfStateName@Broker@@YAJPEAU_WNF_STATE_NAME@@IPEAX1K@Z; Broker::CreateTemporaryWnfStateName(_WNF_STATE_NAME *,uint,void *,void *,ulong)
0x180013170  test    eax, eax
0x180013172  jns     short loc_180013178
0x180013174  mov     [rsi+48h], r12
0x180013178  mov     r8, rbp; unsigned int
0x18001317b  lea     rcx, [rsi+50h]; this
0x18001317f  call    ?CreateTemporaryWnfStateName@Broker@@YAJPEAU_WNF_STATE_NAME@@IPEAX1K@Z; Broker::CreateTemporaryWnfStateName(_WNF_STATE_NAME *,uint,void *,void *,ulong)
0x180013184  test    eax, eax
0x180013186  jns     short loc_18001318C
0x180013188  mov     [rsi+50h], r12
0x18001318c  mov     rax, rsi
0x18001318f  lea     r11, [rsp+78h+var_28]
0x180013194  mov     rbx, [r11+38h]
0x180013198  mov     rbp, [r11+40h]
0x18001319c  mov     rsp, r11
0x18001319f  pop     r15
0x1800131a1  pop     r14
0x1800131a3  pop     r12
0x1800131a5  pop     rdi
0x1800131a6  pop     rsi
0x1800131a7  retn
```
