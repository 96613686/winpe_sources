# CSetDefaultKeyJob::GetDeviceCommandData(void *,uint,uint *,uint *,uint,ulong *,ulong *,uchar * *)

- ea: `0x140077e40`
- end: `0x14007842b`
- name: `?GetDeviceCommandData@CSetDefaultKeyJob@@UEAAHPEAXIPEAI1IPEAK2PEAPEAE@Z`
- size: `1515`
- prototype: `__int64 __usercall@<rax>(CSetDefaultKeyJob *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned int *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14000688c`
- `0x140009420`
- `0x14000c940`
- `0x14000d054`
- `0x140019c78`
- `0x140019d44`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140023ef4`
- `0x14002bd34`
- `0x14002ed50`
- `0x14002ef48`
- `0x14003ff68`
- `0x14004018c`
- `0x140050660`
- `0x140071720`
- `0x140073410`
- `0x1400742b4`
- `0x140074344`
- `0x140076c54`
- `0x140076d48`
- `0x140076e74`
- `0x140077494`
- `0x140077e40`
- `0x1400798dc`
- `0x14008b344`
- `0x14008c180`

## pseudocode

```c
__int64 __fastcall CSetDefaultKeyJob::GetDeviceCommandData(
        CSetDefaultKeyJob *this,
        char *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned __int8 **a9)
{
  unsigned __int16 v10; // dx
  CAdapter *v12; // rcx
  int v15; // edx
  struct CPort *PortFromPortId; // r14
  __int64 *v17; // r8
  unsigned int *v18; // rcx
  unsigned int v19; // edx
  unsigned int v20; // eax
  unsigned int PropertyList; // edi
  int v22; // r9d
  unsigned int KeyTypeFromKeyIndex; // r15d
  _QWORD *v24; // rax
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v25; // rdi
  int v26; // r9d
  unsigned int *v27; // rsi
  int v28; // r9d
  unsigned int v29; // edx
  unsigned int WdiSetAddCipherKeysToIhv; // eax
  int v31; // r9d
  void *v32; // rax
  void *v33; // rdi
  int v34; // eax
  int v35; // eax
  __int64 v36; // r9
  int v37; // eax
  unsigned int v38; // edx
  __int64 v39; // r9
  unsigned __int8 **v40; // rax
  __int64 v41; // rax
  CPropertyCache *PortPropertyCache; // rax
  CPropertyCache *v43; // rax
  __int128 v44; // xmm1
  int v45; // eax
  unsigned __int8 **v47; // [rsp+20h] [rbp-C1h]
  char v48; // [rsp+28h] [rbp-B9h]
  int v49; // [rsp+30h] [rbp-B1h]
  int v50; // [rsp+30h] [rbp-B1h]
  __int64 v51; // [rsp+38h] [rbp-A9h]
  int v52; // [rsp+38h] [rbp-A9h]
  int v53; // [rsp+40h] [rbp-A1h]
  unsigned __int8 *v54[2]; // [rsp+70h] [rbp-71h] BYREF
  int v55; // [rsp+80h] [rbp-61h] BYREF
  void *v56; // [rsp+88h] [rbp-59h]
  char v57; // [rsp+90h] [rbp-51h]
  int v58; // [rsp+98h] [rbp-49h] BYREF
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v59; // [rsp+A0h] [rbp-41h]
  char v60; // [rsp+A8h] [rbp-39h]
  _OWORD v61[2]; // [rsp+B0h] [rbp-31h] BYREF
  int v62; // [rsp+D0h] [rbp-11h]

  v10 = *((_WORD *)this + 26);
  v12 = (CAdapter *)*((_QWORD *)this + 67);
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  PortFromPortId = CAdapter::GetPortFromPortId(v12, v10);
  v17 = WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v15) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      (unsigned int)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      59,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
    v17 = WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids;
  }
  v18 = a5;
  *a4 = 0;
  *v18 = 0;
  v19 = (unsigned __int8)*a2;
  if ( (_BYTE)v19 != 0x80 || !a2[1] || *((_WORD *)a2 + 1) < 0x18u )
  {
    PropertyList = -1073676267;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_qDdddddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        (unsigned int)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
        60,
        (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        128,
        1,
        24,
        *a2,
        a2[1],
        *((_WORD *)a2 + 1));
    }
    goto LABEL_55;
  }
  v20 = *((unsigned __int16 *)a2 + 10) + 22;
  *v18 = v20;
  if ( a3 < v20 )
  {
    PropertyList = -2147483643;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_55;
    LOBYTE(v53) = a3;
    v22 = 61;
    LOBYTE(v52) = v20;
    v49 = *((_DWORD *)this + 4);
    v48 = (char)this;
    goto LABEL_11;
  }
  *a4 = v20;
  KeyTypeFromKeyIndex = CSetDefaultKeyHelpers::GetKeyTypeFromKeyIndex(*((unsigned int *)a2 + 1));
  if ( KeyTypeFromKeyIndex )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = 4;
      WPP_RECORDER_SF_qDddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        (_DWORD)v17,
        63,
        (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        KeyTypeFromKeyIndex,
        *((_DWORD *)a2 + 2),
        *((_DWORD *)a2 + 1));
    }
    if ( a2[18] )
    {
      v32 = operator new(0x24u);
      v33 = v32;
      if ( v32 )
      {
        `vector constructor iterator'(
          v32,
          0x24u,
          1u,
          (void *(*)(void *))_WDI_SET_DELETE_CIPHER_KEYS_CONTAINER::_WDI_SET_DELETE_CIPHER_KEYS_CONTAINER);
        v56 = v33;
      }
      else
      {
        v56 = 0;
      }
      if ( !v56 )
      {
        PropertyList = -1073741670;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_55;
        v26 = 67;
        goto LABEL_24;
      }
      v34 = *((_DWORD *)a2 + 1);
      v55 = 1;
      *((_DWORD *)v56 + 3) = v34;
      v35 = CDot11ToWabiConverter::MapCipherAlgorithm(*((unsigned int *)a2 + 2));
      *(_DWORD *)(v36 + 16) = v35;
      v37 = CDot11ToWabiConverter::MapP2PScanType(3);
      v38 = a6;
      *(_DWORD *)(v39 + 20) = v37;
      *(_DWORD *)(v39 + 28) = KeyTypeFromKeyIndex;
      *(_BYTE *)(v39 + 24) = a2[19];
      *(_DWORD *)(v39 + 4) = *((_DWORD *)a2 + 3);
      LOWORD(v37) = *((_WORD *)a2 + 8);
      v27 = a7;
      *(_WORD *)(v39 + 8) = v37;
      v40 = a9;
      LODWORD(v39) = (_DWORD)a8;
      *v27 = 30;
      WdiSetAddCipherKeysToIhv = GenerateWdiSetDeleteCipherKeysToIhv(
                                   (unsigned int)&v55,
                                   v38,
                                   (unsigned int)*((_QWORD *)this + 67) + 5384,
                                   v39,
                                   (__int64)v40);
      PropertyList = WdiSetAddCipherKeysToIhv;
      if ( WdiSetAddCipherKeysToIhv )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_55;
        v31 = 68;
LABEL_32:
        LOBYTE(v19) = 2;
        LODWORD(v51) = WdiSetAddCipherKeysToIhv;
        WPP_RECORDER_SF_qDD(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          (_DWORD)v17,
          v31,
          (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v51);
        goto LABEL_55;
      }
    }
    else
    {
      v24 = operator new(0x110u);
      if ( v24 )
      {
        v25 = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER *)(v24 + 1);
        *v24 = 1;
        `vector constructor iterator'(
          v24 + 1,
          0x108u,
          1u,
          (void *(*)(void *))_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER);
        v59 = v25;
      }
      else
      {
        v25 = 0;
        v59 = 0;
      }
      if ( !v25 )
      {
        PropertyList = -1073741670;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_57;
        v26 = 64;
LABEL_24:
        v50 = *((_DWORD *)this + 4);
        goto LABEL_25;
      }
      v58 = 1;
      PropertyList = CSetDefaultKeyHelpers::FillSetCipherKeyParameters(KeyTypeFromKeyIndex, a2, v25);
      if ( PropertyList )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_55;
        v26 = 65;
        v50 = *((_DWORD *)this + 4);
LABEL_25:
        LOBYTE(v19) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          (_DWORD)v17,
          v26,
          (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
          (char)this,
          v50);
        goto LABEL_55;
      }
      v27 = a7;
      v28 = (int)a8;
      v29 = a6;
      v47 = a9;
      *a7 = 29;
      WdiSetAddCipherKeysToIhv = GenerateWdiSetAddCipherKeysToIhv(
                                   (unsigned int)&v58,
                                   v29,
                                   (unsigned int)*((_QWORD *)this + 67) + 5384,
                                   v28,
                                   (__int64)v47);
      PropertyList = WdiSetAddCipherKeysToIhv;
      if ( WdiSetAddCipherKeysToIhv )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_55;
        v31 = 66;
        goto LABEL_32;
      }
    }
    v41 = *((_QWORD *)PortFromPortId + 9);
    if ( v41 && *(_BYTE *)(v41 + 1) )
    {
      *(_QWORD *)(*((_QWORD *)PortFromPortId + 9) + 120LL) = CSystem::get_CurrentTime();
      CPort::TraceLoggingRoamFinished(PortFromPortId, 0);
    }
    if ( *v27 == 29 )
    {
      PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
      if ( CPropertyCache::GetPropertyBooleanOrDefault(PortPropertyCache, 0x14u, 0) )
      {
        LODWORD(a5) = 0;
        *(_OWORD *)v54 = 0;
        v43 = COidJobBase::GetPortPropertyCache(this);
        PropertyList = CPropertyCache::GetPropertyList(v43, 5u, (unsigned int *)&a5, (unsigned __int16 *)v54, &v54[1]);
        if ( !PropertyList )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v19) = 4;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v19,
              PropertyList + 1,
              69,
              (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids);
          }
          v44 = *((_OWORD *)v54[1] + 1);
          v45 = *((_DWORD *)v54[1] + 8);
          v61[0] = *(_OWORD *)v54[1];
          v61[1] = v44;
          v62 = v45;
          CPort::UnBlockSSIDFor11r(PortFromPortId, v61);
        }
      }
      if ( KeyTypeFromKeyIndex == 3 )
        CPort::AddCurrentConnectionFlag(PortFromPortId, v19);
    }
    goto LABEL_55;
  }
  PropertyList = -1073676267;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v22 = 62;
    v53 = *((_DWORD *)a2 + 1);
    v52 = *((_DWORD *)a2 + 2);
    v49 = *((_DWORD *)this + 4);
    v48 = (char)this;
LABEL_11:
    LOBYTE(v19) = 2;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      (_DWORD)v17,
      v22,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      v48,
      v49,
      v52,
      v53);
  }
LABEL_55:
  if ( v59 )
    _WDI_SET_ADD_CIPHER_KEYS_CONTAINER::`vector deleting destructor'(v59, 3u);
LABEL_57:
  if ( v56 )
    operator delete(v56);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v19) = 5;
    LODWORD(v51) = PropertyList;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      (_DWORD)v17,
      70,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v51);
  }
  ArrayOfElements<_WDI_PHY_STATISTICS_PARAMETERS>::Cleanup(&v55);
  ArrayOfElements<_WDI_SET_ADD_CIPHER_KEYS_CONTAINER>::Cleanup(&v58);
  return PropertyList;
}

```

## disassembly

```asm
0x140077e40  push    rbp
0x140077e42  push    rbx
0x140077e43  push    rsi
0x140077e44  push    rdi
0x140077e45  push    r12
0x140077e47  push    r13
0x140077e49  push    r14
0x140077e4b  push    r15
0x140077e4d  lea     rbp, [rsp-7]
0x140077e52  sub     rsp, 0E8h
0x140077e59  xor     r12d, r12d
0x140077e5c  mov     rsi, rdx
0x140077e5f  movzx   edx, word ptr [rcx+34h]; unsigned __int16
0x140077e63  mov     rbx, rcx
0x140077e66  mov     rcx, [rcx+218h]; this
0x140077e6d  mov     rdi, r9
0x140077e70  mov     r15d, r8d
0x140077e73  mov     [rbp+3Fh+var_88], r12d
0x140077e77  mov     [rbp+3Fh+var_80], r12
0x140077e7b  mov     [rbp+3Fh+var_78], r12b
0x140077e7f  mov     [rbp+3Fh+var_A0], r12d
0x140077e83  mov     [rbp+3Fh+var_98], r12
0x140077e87  mov     [rbp+3Fh+var_90], r12b
0x140077e8b  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x140077e90  mov     r14, rax
0x140077e93  lea     r13, WPP_RECORDER_INITIALIZED
0x140077e9a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140077ea1  lea     r8, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140077ea8  jz      short loc_140077EE7
0x140077eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x140077eb1  cmp     byte ptr [rcx+29h], 5
0x140077eb5  jnb     short loc_140077EBE
0x140077eb7  cmp     [rcx+48h], r12w
0x140077ebc  jz      short loc_140077EE7
0x140077ebe  mov     eax, [rbx+10h]
0x140077ec1  mov     r9d, 3Bh ; ';'
0x140077ec7  mov     rcx, [rcx+40h]
0x140077ecb  mov     dl, 5
0x140077ecd  mov     [rsp+120h+var_F0], eax
0x140077ed1  mov     [rsp+120h+var_F8], rbx
0x140077ed6  mov     [rsp+120h+var_100], r8
0x140077edb  call    WPP_RECORDER_SF_qD
0x140077ee0  lea     r8, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140077ee7  mov     rcx, [rbp+3Fh+arg_20]
0x140077eeb  mov     r10d, 18h
0x140077ef1  mov     [rdi], r12d
0x140077ef4  mov     [rcx], r12d
0x140077ef7  movzx   edx, byte ptr [rsi]
0x140077efa  cmp     dl, 80h
0x140077efd  jnz     loc_140078337
0x140077f03  cmp     byte ptr [rsi+1], 1
0x140077f07  jb      loc_140078337
0x140077f0d  cmp     [rsi+2], r10w
0x140077f12  jb      loc_140078337
0x140077f18  movzx   eax, word ptr [rsi+14h]
0x140077f1c  add     eax, 16h
0x140077f1f  mov     [rcx], eax
0x140077f21  cmp     r15d, eax
0x140077f24  jnb     short loc_140077F6D
0x140077f26  mov     edi, 80000005h
0x140077f2b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140077f32  jz      loc_140078397
0x140077f38  mov     [rsp+120h+var_E0], r15d
0x140077f3d  lea     r9d, [r10+25h]
0x140077f41  mov     dword ptr [rsp+120h+var_E8], eax
0x140077f45  mov     eax, [rbx+10h]
0x140077f48  mov     [rsp+120h+var_F0], eax
0x140077f4c  mov     [rsp+120h+var_F8], rbx
0x140077f51  mov     [rsp+120h+var_100], r8
0x140077f56  mov     rcx, cs:WPP_GLOBAL_Control
0x140077f5d  mov     dl, 2
0x140077f5f  mov     rcx, [rcx+40h]
0x140077f63  call    WPP_RECORDER_SF_qDdd
0x140077f68  jmp     loc_140078397
0x140077f6d  mov     [rdi], eax
0x140077f6f  mov     ecx, [rsi+4]
0x140077f72  call    ?GetKeyTypeFromKeyIndex@CSetDefaultKeyHelpers@@SA?AW4_WDI_CIPHER_KEY_TYPE@@K@Z; CSetDefaultKeyHelpers::GetKeyTypeFromKeyIndex(ulong)
0x140077f77  mov     r15d, eax
0x140077f7a  test    eax, eax
0x140077f7c  jnz     short loc_140077FBC
0x140077f7e  mov     edi, 0C0010015h
0x140077f83  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140077f8a  jz      loc_140078397
0x140077f90  lea     r9d, [rax+3Eh]
0x140077f94  mov     eax, [rsi+4]
0x140077f97  mov     [rsp+120h+var_E0], eax
0x140077f9b  mov     eax, [rsi+8]
0x140077f9e  mov     dword ptr [rsp+120h+var_E8], eax
0x140077fa2  mov     eax, [rbx+10h]
0x140077fa5  mov     [rsp+120h+var_F0], eax
0x140077fa9  lea     rax, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140077fb0  mov     [rsp+120h+var_F8], rbx
0x140077fb5  mov     [rsp+120h+var_100], rax
0x140077fba  jmp     short loc_140077F56
0x140077fbc  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140077fc3  jz      short loc_140078008
0x140077fc5  mov     eax, [rsi+4]
0x140077fc8  mov     r9d, 3Fh ; '?'
0x140077fce  mov     rcx, cs:WPP_GLOBAL_Control
0x140077fd5  mov     dl, 4
0x140077fd7  mov     [rsp+120h+var_D8], eax
0x140077fdb  mov     eax, [rsi+8]
0x140077fde  mov     [rsp+120h+var_E0], eax
0x140077fe2  mov     eax, [rbx+10h]
0x140077fe5  mov     rcx, [rcx+40h]
0x140077fe9  mov     dword ptr [rsp+120h+var_E8], r15d
0x140077fee  mov     [rsp+120h+var_F0], eax
0x140077ff2  lea     rax, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140077ff9  mov     [rsp+120h+var_F8], rbx
0x140077ffe  mov     [rsp+120h+var_100], rax
0x140078003  call    WPP_RECORDER_SF_qDddd
0x140078008  cmp     [rsi+12h], r12b
0x14007800c  jnz     loc_14007815B
0x140078012  mov     ecx, 110h; unsigned __int64
0x140078017  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007801c  test    rax, rax
0x14007801f  jz      short loc_14007804A
0x140078021  mov     ecx, 1
0x140078026  lea     rdi, [rax+8]
0x14007802a  mov     [rax], rcx
0x14007802d  lea     r9, ??0_WDI_SET_ADD_CIPHER_KEYS_CONTAINER@@QEAA@XZ; void *(*)(void *)
0x140078034  mov     r8d, ecx; unsigned __int64
0x140078037  mov     edx, 108h; unsigned __int64
0x14007803c  mov     rcx, rdi; void *
0x14007803f  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x140078044  mov     [rbp+3Fh+var_80], rdi
0x140078048  jmp     short loc_140078051
0x14007804a  mov     rdi, r12
0x14007804d  mov     [rbp+3Fh+var_80], r12
0x140078051  test    rdi, rdi
0x140078054  jnz     short loc_14007809D
0x140078056  mov     edi, 0C000009Ah
0x14007805b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140078062  jz      loc_1400783AA
0x140078068  mov     r9d, 40h ; '@'
0x14007806e  mov     eax, [rbx+10h]
0x140078071  mov     [rsp+120h+var_F0], eax
0x140078075  mov     rcx, cs:WPP_GLOBAL_Control
0x14007807c  lea     rax, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140078083  mov     [rsp+120h+var_F8], rbx
0x140078088  mov     dl, 2
0x14007808a  mov     [rsp+120h+var_100], rax
0x14007808f  mov     rcx, [rcx+40h]
0x140078093  call    WPP_RECORDER_SF_qD
0x140078098  jmp     loc_140078397
0x14007809d  mov     r8, rdi
0x1400780a0  mov     [rbp+3Fh+var_88], 1
0x1400780a7  mov     rdx, rsi
0x1400780aa  mov     ecx, r15d
0x1400780ad  call    ?FillSetCipherKeyParameters@CSetDefaultKeyHelpers@@SAHW4_WDI_CIPHER_KEY_TYPE@@PEAUDOT11_CIPHER_DEFAULT_KEY_VALUE@@PEAU_WDI_SET_ADD_CIPHER_KEYS_CONTAINER@@@Z; CSetDefaultKeyHelpers::FillSetCipherKeyParameters(_WDI_CIPHER_KEY_TYPE,DOT11_CIPHER_DEFAULT_KEY_VALUE *,_WDI_SET_ADD_CIPHER_KEYS_CONTAINER *)
0x1400780b2  mov     edi, eax
0x1400780b4  test    eax, eax
0x1400780b6  jz      short loc_1400780D4
0x1400780b8  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400780bf  jz      loc_140078397
0x1400780c5  mov     ecx, [rbx+10h]
0x1400780c8  mov     r9d, 41h ; 'A'
0x1400780ce  mov     [rsp+120h+var_F0], ecx
0x1400780d2  jmp     short loc_140078075
0x1400780d4  mov     rax, [rbp+3Fh+arg_40]
0x1400780db  lea     rcx, [rbp+3Fh+var_88]
0x1400780df  mov     rsi, [rbp+3Fh+arg_30]
0x1400780e3  mov     r9, [rbp+3Fh+arg_38]
0x1400780ea  mov     edx, [rbp+3Fh+arg_28]
0x1400780ed  mov     [rsp+120h+var_100], rax
0x1400780f2  mov     dword ptr [rsi], 1Dh
0x1400780f8  mov     r8, [rbx+218h]
0x1400780ff  add     r8, 1508h
0x140078106  call    GenerateWdiSetAddCipherKeysToIhv
0x14007810b  mov     edi, eax
0x14007810d  test    eax, eax
0x14007810f  jz      loc_14007824E
0x140078115  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14007811c  jz      loc_140078397
0x140078122  mov     r9d, 42h ; 'B'
0x140078128  mov     rcx, cs:WPP_GLOBAL_Control
0x14007812f  mov     dl, 2
0x140078131  mov     dword ptr [rsp+120h+var_E8], eax
0x140078135  mov     eax, [rbx+10h]
0x140078138  mov     [rsp+120h+var_F0], eax
0x14007813c  lea     rax, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140078143  mov     rcx, [rcx+40h]
0x140078147  mov     [rsp+120h+var_F8], rbx
0x14007814c  mov     [rsp+120h+var_100], rax
0x140078151  call    WPP_RECORDER_SF_qDD
0x140078156  jmp     loc_140078397
0x14007815b  mov     ecx, 24h ; '$'; unsigned __int64
0x140078160  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140078165  mov     rdi, rax
0x140078168  test    rax, rax
0x14007816b  jz      short loc_14007818B
0x14007816d  mov     edx, 24h ; '$'; unsigned __int64
0x140078172  lea     r9, ??0_WDI_SET_DELETE_CIPHER_KEYS_CONTAINER@@QEAA@XZ; void *(*)(void *)
0x140078179  mov     rcx, rax; void *
0x14007817c  lea     r8d, [rdx-23h]; unsigned __int64
0x140078180  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x140078185  mov     [rbp+3Fh+var_98], rdi
0x140078189  jmp     short loc_14007818F
0x14007818b  mov     [rbp+3Fh+var_98], r12
0x14007818f  cmp     [rbp+3Fh+var_98], r12
0x140078193  jnz     short loc_1400781B2
0x140078195  mov     edi, 0C000009Ah
0x14007819a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400781a1  jz      loc_140078397
0x1400781a7  mov     r9d, 43h ; 'C'
0x1400781ad  jmp     loc_14007806E
0x1400781b2  mov     eax, [rsi+4]
0x1400781b5  mov     r9, [rbp+3Fh+var_98]
0x1400781b9  mov     [rbp+3Fh+var_A0], 1
0x1400781c0  mov     [r9+0Ch], eax
0x1400781c4  mov     ecx, [rsi+8]
0x1400781c7  call    ?MapCipherAlgorithm@CDot11ToWabiConverter@@SA?AW4_WDI_CIPHER_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@@Z; CDot11ToWabiConverter::MapCipherAlgorithm(_DOT11_CIPHER_ALGORITHM)
0x1400781cc  mov     ecx, 3
0x1400781d1  mov     [r9+10h], eax
0x1400781d5  call    ?MapP2PScanType@CDot11ToWabiConverter@@SA?AW4_WDI_P2P_SCAN_TYPE@@W4_DOT11_WFD_SCAN_TYPE@@@Z; CDot11ToWabiConverter::MapP2PScanType(_DOT11_WFD_SCAN_TYPE)
0x1400781da  mov     edx, [rbp+3Fh+arg_28]
0x1400781dd  lea     rcx, [rbp+3Fh+var_A0]
0x1400781e1  mov     [r9+14h], eax
0x1400781e5  mov     [r9+1Ch], r15d
0x1400781e9  mov     al, [rsi+13h]
0x1400781ec  mov     [r9+18h], al
0x1400781f0  mov     eax, [rsi+0Ch]
0x1400781f3  mov     [r9+4], eax
0x1400781f7  movzx   eax, word ptr [rsi+10h]
0x1400781fb  mov     rsi, [rbp+3Fh+arg_30]
0x1400781ff  mov     [r9+8], ax
0x140078204  mov     rax, [rbp+3Fh+arg_40]
0x14007820b  mov     r9, [rbp+3Fh+arg_38]
0x140078212  mov     dword ptr [rsi], 1Eh
0x140078218  mov     r8, [rbx+218h]
0x14007821f  add     r8, 1508h
0x140078226  mov     [rsp+120h+var_100], rax
0x14007822b  call    GenerateWdiSetDeleteCipherKeysToIhv
0x140078230  mov     edi, eax
0x140078232  test    eax, eax
0x140078234  jz      short loc_14007824E
0x140078236  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14007823d  jz      loc_140078397
0x140078243  mov     r9d, 44h ; 'D'
0x140078249  jmp     loc_140078128
0x14007824e  mov     rax, [r14+48h]
0x140078252  test    rax, rax
0x140078255  jz      short loc_140078274
0x140078257  cmp     [rax+1], r12b
0x14007825b  jz      short loc_140078274
0x14007825d  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x140078262  mov     rcx, [r14+48h]
0x140078266  xor     edx, edx; int
0x140078268  mov     [rcx+78h], rax
0x14007826c  mov     rcx, r14; this
0x14007826f  call    ?TraceLoggingRoamFinished@CPort@@QEAAXH@Z; CPort::TraceLoggingRoamFinished(int)
0x140078274  cmp     dword ptr [rsi], 1Dh
0x140078277  jnz     loc_140078397
0x14007827d  mov     rcx, rbx; this
0x140078280  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x140078285  xor     r8d, r8d; unsigned __int8
0x140078288  mov     rcx, rax; this
0x14007828b  lea     edx, [r8+14h]; unsigned int
0x14007828f  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x140078294  test    al, al
0x140078296  jz      loc_140078327
0x14007829c  xorps   xmm0, xmm0
0x14007829f  mov     dword ptr [rbp+3Fh+arg_20], r12d
0x1400782a3  mov     rcx, rbx; this
0x1400782a6  movups  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x1400782aa  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400782af  lea     rcx, [rbp+3Fh+var_B0+8]
0x1400782b3  mov     edx, 5; unsigned int
0x1400782b8  mov     [rsp+120h+var_100], rcx; unsigned __int8 **
0x1400782bd  lea     r9, [rbp+3Fh+var_B0]; unsigned __int16 *
0x1400782c1  mov     rcx, rax; this
0x1400782c4  lea     r8, [rbp+3Fh+arg_20]; unsigned int *
0x1400782c8  call    ?GetPropertyList@CPropertyCache@@QEBAHKPEAKPEAGPEAPEAE@Z; CPropertyCache::GetPropertyList(ulong,ulong *,ushort *,uchar * *)
0x1400782cd  mov     edi, eax
0x1400782cf  test    eax, eax
0x1400782d1  jnz     short loc_140078327
0x1400782d3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400782da  jz      short loc_140078302
0x1400782dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400782e3  lea     r9d, [rax+45h]
0x1400782e7  lea     rax, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x1400782ee  mov     dl, 4
0x1400782f0  lea     r8d, [rdi+1]
0x1400782f4  mov     [rsp+120h+var_100], rax
0x1400782f9  mov     rcx, [rcx+40h]
0x1400782fd  call    WPP_RECORDER_SF_
0x140078302  mov     rax, [rbp+3Fh+var_B0+8]
0x140078306  lea     rdx, [rbp+3Fh+var_70]
0x14007830a  mov     rcx, r14
0x14007830d  movups  xmm0, xmmword ptr [rax]
0x140078310  movups  xmm1, xmmword ptr [rax+10h]
0x140078314  mov     eax, [rax+20h]
0x140078317  movaps  [rbp+3Fh+var_70], xmm0
0x14007831b  movaps  [rbp+3Fh+var_60], xmm1
0x14007831f  mov     [rbp+3Fh+var_50], eax
0x140078322  call    ?UnBlockSSIDFor11r@CPort@@QEAAXU_DOT11_SSID@@W4_WFC_BLOCKED_REASON@@@Z; CPort::UnBlockSSIDFor11r(_DOT11_SSID,_WFC_BLOCKED_REASON)
0x140078327  cmp     r15d, 3
0x14007832b  jnz     short loc_140078397
0x14007832d  mov     rcx, r14; this
0x140078330  call    ?AddCurrentConnectionFlag@CPort@@QEAAXK@Z; CPort::AddCurrentConnectionFlag(ulong)
  ... truncated ...
```
