# NDXGI::CDevice::CreateExistingSysMemStandardAllocation(void *,void const *,unsigned __int64,void const *,uint,void * *)

- ea: `0x180050610`
- end: `0x180050817`
- name: `?CreateExistingSysMemStandardAllocation@CDevice@NDXGI@@QEAAXPEAXPEBX_K1IPEAPEAX@Z`
- size: `519`
- prototype: `void __fastcall(NDXGI::CDevice *__hidden this, void *, const void *, unsigned __int64, const void *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18004fee0`
- `0x1800f82f0`

## callees

- `0x1800074c4`
- `0x180007df0`
- `0x18000b010`
- `0x180050610`
- `0x180050b94`
- `0x1800bb480`
- `0x1800bc094`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCreateAllocation2` at `0x1800506f2`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTShareObjects` at `0x180050784`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTDestroyAllocation2` at `0x1800507fb`

## string_xrefs

- `0x1800506eb`: `CreateAllocation2 - StandardAllocation`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall NDXGI::CDevice::CreateExistingSysMemStandardAllocation(
        NDXGI::CDevice *this,
        void *a2,
        void *a3,
        __int64 a4,
        const void *a5,
        unsigned int a6,
        void **a7)
{
  void *v10; // rax
  __int64 v11; // r8
  unsigned int v12; // eax
  int v13; // eax
  int v14; // edx
  int v15; // r8d
  unsigned int v16; // eax
  int v17; // eax
  __int64 v18; // r8
  unsigned int v19; // eax
  int *v20; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v21; // [rsp+48h] [rbp-B8h]
  __int128 v22; // [rsp+60h] [rbp-A0h]
  __int64 v23; // [rsp+70h] [rbp-90h]
  __int128 v24; // [rsp+78h] [rbp-88h]
  _OWORD v25[3]; // [rsp+88h] [rbp-78h] BYREF
  _OWORD *v26; // [rsp+B8h] [rbp-48h]
  int v27; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v28[3]; // [rsp+C4h] [rbp-3Ch] BYREF
  const void *v29; // [rsp+D0h] [rbp-30h]
  int v30; // [rsp+D8h] [rbp-28h]
  _QWORD *v31; // [rsp+E0h] [rbp-20h]
  int v32; // [rsp+ECh] [rbp-14h]
  _BYTE *v33; // [rsp+F0h] [rbp-10h]
  int v34; // [rsp+F8h] [rbp-8h]
  _BYTE v35[8]; // [rsp+110h] [rbp+10h] BYREF
  void *v36; // [rsp+118h] [rbp+18h]
  _QWORD v37[3]; // [rsp+170h] [rbp+70h] BYREF

  v37[0] = 1;
  v37[2] = 0;
  v37[1] = a4;
  memset_0(v35, 0, 0x60u);
  v10 = v36;
  if ( a2 )
    v10 = a2;
  if ( a3 )
    v10 = a3;
  v36 = v10;
  memset_0(&v27, 0, 0x48u);
  v27 = *((_DWORD *)this + 14);
  v29 = a5;
  v30 = 280;
  v31 = v37;
  v32 = 1;
  v33 = v35;
  v34 = (a3 != 0 ? 0x20 : 0) | (a2 != 0 ? 198723 : 67651);
  v12 = CallAndLogImpl<long (*)(_D3DKMT_CREATEALLOCATION *),_D3DKMT_CREATEALLOCATION *>(
          D3DKMTCreateAllocation2,
          "CreateAllocation2 - StandardAllocation",
          v11,
          &v27);
  v13 = NDXGI::CDevice::NTStatusToHResult(this, v12, 1);
  ThrowFailure(v13);
  v20 = &v27;
  *(_QWORD *)&v21 = this;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25[0] = 0x30u;
  memset(&v25[1], 0, 32);
  v26 = v25;
  v16 = CallAndLogImpl<long (*)(unsigned int,unsigned int const *,_OBJECT_ATTRIBUTES *,unsigned long,void * *),unsigned int,unsigned int const *,_OBJECT_ATTRIBUTES *,unsigned long,void * *>(
          D3DKMTShareObjects,
          v14,
          v15,
          1,
          (__int64)v28,
          (__int64)v25,
          0x10000000,
          (__int64)a7);
  v17 = NDXGI::CDevice::NTStatusToHResult(this, v16, 1);
  if ( v17 == -2147024890 )
    v17 = -2005270484;
  ThrowFailure(v17);
  if ( v28[0] )
  {
    v21 = 0;
    LODWORD(v20) = *((_DWORD *)this + 14);
    HIDWORD(v20) = v28[0];
    v19 = CallAndLogImpl<long (*)(_D3DKMT_CREATEALLOCATION *),_D3DKMT_CREATEALLOCATION *>(
            D3DKMTDestroyAllocation2,
            "DestroyAllocation2 - StandardAllocation",
            v18,
            &v20);
    NDXGI::CDevice::NTStatusToHResult(this, v19, 1);
  }
}

```

## disassembly

```asm
0x180050610  push    rbp
0x180050612  push    rbx
0x180050613  push    rsi
0x180050614  push    rdi
0x180050615  push    r13
0x180050617  push    r14
0x180050619  push    r15
0x18005061b  lea     rbp, [rsp-90h]
0x180050623  sub     rsp, 190h
0x18005062a  mov     rax, cs:__security_cookie
0x180050631  xor     rax, rsp
0x180050634  mov     [rbp+0C0h+var_38], rax
0x18005063b  mov     rsi, r8
0x18005063e  mov     rdi, rdx
0x180050641  mov     r15, rcx
0x180050644  mov     rbx, [rbp+0C0h+arg_20]
0x18005064b  mov     r14, [rbp+0C0h+arg_30]
0x180050652  mov     [rbp+0C0h+var_50], 1
0x18005065a  mov     [rbp+0C0h+var_40], 0
0x180050665  mov     r13d, 1
0x18005066b  mov     [rbp+0C0h+var_48], r9
0x18005066f  xor     edx, edx; Val
0x180050671  lea     r8d, [r13+5Fh]; Size
0x180050675  lea     rcx, [rbp+0C0h+var_B0]; void *
0x180050679  call    memset_0
0x18005067e  mov     rax, [rbp+0C0h+var_A8]
0x180050682  test    rdi, rdi
0x180050685  cmovnz  rax, rdi
0x180050689  test    rsi, rsi
0x18005068c  cmovnz  rax, rsi
0x180050690  mov     [rbp+0C0h+var_A8], rax
0x180050694  xor     edx, edx; Val
0x180050696  lea     r8d, [r13+47h]; Size
0x18005069a  lea     rcx, [rbp+0C0h+var_100]; void *
0x18005069e  call    memset_0
0x1800506a3  mov     eax, [r15+38h]
0x1800506a7  mov     [rbp+0C0h+var_100], eax
0x1800506aa  mov     [rbp+0C0h+var_F0], rbx
0x1800506ae  mov     [rbp+0C0h+var_E8], 118h
0x1800506b5  lea     rax, [rbp+0C0h+var_50]
0x1800506b9  mov     [rbp+0C0h+var_E0], rax
0x1800506bd  mov     [rbp+0C0h+var_D4], r13d
0x1800506c1  lea     rax, [rbp+0C0h+var_B0]
0x1800506c5  mov     [rbp+0C0h+var_D0], rax
0x1800506c9  neg     rdi
0x1800506cc  sbb     ecx, ecx
0x1800506ce  and     ecx, 20000h
0x1800506d4  add     ecx, 10843h
0x1800506da  neg     rsi
0x1800506dd  sbb     eax, eax
0x1800506df  and     eax, 20h
0x1800506e2  or      ecx, eax
0x1800506e4  mov     [rbp+0C0h+var_C8], ecx
0x1800506e7  lea     r9, [rbp+0C0h+var_100]
0x1800506eb  lea     rdx, aCreateallocati_0; "CreateAllocation2 - StandardAllocation"
0x1800506f2  mov     rcx, cs:__imp_D3DKMTCreateAllocation2
0x1800506f9  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_CREATEALLOCATION@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_CREATEALLOCATION@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(_D3DKMT_CREATEALLOCATION *),_D3DKMT_CREATEALLOCATION *>(long (*)(_D3DKMT_CREATEALLOCATION *),char const *,RecordStatusFilterResult (*)(long),_D3DKMT_CREATEALLOCATION *)
0x1800506fe  mov     r8d, r13d
0x180050701  mov     edx, eax
0x180050703  mov     rcx, r15
0x180050706  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x18005070b  mov     ecx, eax; int
0x18005070d  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180050712  lea     rax, [rbp+0C0h+var_100]
0x180050716  mov     [rsp+1C0h+var_180], rax
0x18005071b  mov     qword ptr [rsp+1C0h+var_178], r15
0x180050720  xor     eax, eax
0x180050722  xorps   xmm0, xmm0
0x180050725  movups  [rsp+1C0h+var_160], xmm0
0x18005072a  mov     [rsp+1C0h+var_150], rax
0x18005072f  movups  [rsp+1C0h+var_148], xmm0
0x180050734  movups  [rbp+0C0h+var_138], xmm0
0x180050738  movups  [rbp+0C0h+var_128], xmm0
0x18005073c  movups  [rbp+0C0h+var_118], xmm0
0x180050740  mov     dword ptr [rbp+0C0h+var_138], 30h ; '0'
0x180050747  mov     qword ptr [rbp+0C0h+var_138+8], rax
0x18005074b  mov     dword ptr [rbp+0C0h+var_128+8], eax
0x18005074e  mov     qword ptr [rbp+0C0h+var_128], rax
0x180050752  mov     qword ptr [rbp+0C0h+var_118], rax
0x180050756  mov     qword ptr [rbp+0C0h+var_118+8], rax
0x18005075a  lea     rax, [rbp+0C0h+var_138]
0x18005075e  mov     [rbp+0C0h+var_108], rax
0x180050762  mov     [rsp+1C0h+var_188], r14
0x180050767  mov     [rsp+1C0h+var_190], 10000000h
0x18005076f  lea     rax, [rbp+0C0h+var_138]
0x180050773  mov     [rsp+1C0h+var_198], rax
0x180050778  lea     rax, [rbp+0C0h+var_FC]
0x18005077c  mov     [rsp+1C0h+var_1A0], rax
0x180050781  mov     r9d, r13d
0x180050784  mov     rcx, cs:__imp_D3DKMTShareObjects
0x18005078b  call    ??$CallAndLogImpl@P6AJIPEBIPEAU_OBJECT_ATTRIBUTES@@KPEAPEAX@ZIPEBIPEAU1@KPEAPEAX@@YAJP6AJIPEBIPEAU_OBJECT_ATTRIBUTES@@KPEAPEAX@ZPEBDP6A?AW4RecordStatusFilterResult@@J@ZI01K2@Z; CallAndLogImpl<long (*)(uint,uint const *,_OBJECT_ATTRIBUTES *,ulong,void * *),uint,uint const *,_OBJECT_ATTRIBUTES *,ulong,void * *>(long (*)(uint,uint const *,_OBJECT_ATTRIBUTES *,ulong,void * *),char const *,RecordStatusFilterResult (*)(long),uint,uint const *,_OBJECT_ATTRIBUTES *,ulong,void * *)
0x180050790  mov     r8d, r13d
0x180050793  mov     edx, eax
0x180050795  mov     rcx, r15
0x180050798  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x18005079d  mov     ecx, 887A002Ch
0x1800507a2  cmp     eax, 80070006h
0x1800507a7  cmovz   eax, ecx
0x1800507aa  mov     ecx, eax; int
0x1800507ac  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800507b1  nop
0x1800507b2  mov     ecx, [rbp+0C0h+var_FC]
0x1800507b5  test    ecx, ecx
0x1800507b7  jnz     short loc_1800507DA
0x1800507b9  mov     rcx, [rbp+0C0h+var_38]
0x1800507c0  xor     rcx, rsp; StackCookie
0x1800507c3  call    __security_check_cookie
0x1800507c8  add     rsp, 190h
0x1800507cf  pop     r15
0x1800507d1  pop     r14
0x1800507d3  pop     r13
0x1800507d5  pop     rdi
0x1800507d6  pop     rsi
0x1800507d7  pop     rbx
0x1800507d8  pop     rbp
0x1800507d9  retn
0x1800507da  xorps   xmm0, xmm0
0x1800507dd  movdqu  [rsp+1C0h+var_178], xmm0
0x1800507e3  mov     eax, [r15+38h]
0x1800507e7  mov     dword ptr [rsp+1C0h+var_180], eax
0x1800507eb  mov     dword ptr [rsp+1C0h+var_180+4], ecx
0x1800507ef  lea     r9, [rsp+1C0h+var_180]
0x1800507f4  lea     rdx, aDestroyallocat_0; "DestroyAllocation2 - StandardAllocation"
0x1800507fb  mov     rcx, cs:__imp_D3DKMTDestroyAllocation2
0x180050802  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_CREATEALLOCATION@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_CREATEALLOCATION@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(_D3DKMT_CREATEALLOCATION *),_D3DKMT_CREATEALLOCATION *>(long (*)(_D3DKMT_CREATEALLOCATION *),char const *,RecordStatusFilterResult (*)(long),_D3DKMT_CREATEALLOCATION *)
0x180050807  mov     r8d, r13d
0x18005080a  mov     edx, eax
0x18005080c  mov     rcx, r15
0x18005080f  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x180050814  jmp     short loc_1800507B9
```
