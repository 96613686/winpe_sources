# CSetMloKeysJob::GetDeviceCommandData(void *,uint,uint *,uint *,uint,ulong *,ulong *,uchar * *)

- ea: `0x140078d60`
- end: `0x140079403`
- name: `?GetDeviceCommandData@CSetMloKeysJob@@UEAAHPEAXIPEAI1IPEAK2PEAPEAE@Z`
- size: `1699`
- prototype: `__int64 __usercall@<rax>(CSetMloKeysJob *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned int *, unsigned int, unsigned int *, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14000688c`
- `0x140009420`
- `0x14000d054`
- `0x140019d44`
- `0x14001e2c0`
- `0x14001eed0`
- `0x140023ef4`
- `0x14002bd34`
- `0x14002ed50`
- `0x14002ef48`
- `0x14003ff68`
- `0x140050660`
- `0x140071720`
- `0x140073410`
- `0x140076c54`
- `0x140076d48`
- `0x140076e74`
- `0x140077494`
- `0x140078d60`
- `0x1400798dc`
- `0x14007fa18`
- `0x14007fb64`
- `0x14008b344`
- `0x14008c180`

## pseudocode

```c
__int64 __fastcall CSetMloKeysJob::GetDeviceCommandData(
        CSetMloKeysJob *this,
        void *a2,
        int a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned __int8 **a9)
{
  unsigned int v10; // esi
  unsigned int v12; // ecx
  _DWORD *v13; // rax
  unsigned int *v14; // rax
  unsigned int *v15; // r15
  unsigned int v16; // eax
  __int64 v17; // rsi
  __int64 v18; // rax
  unsigned __int64 v19; // kr00_8
  bool v20; // cf
  unsigned __int64 v21; // rax
  _QWORD *v22; // rax
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v23; // rbx
  unsigned int PropertyList; // ebx
  unsigned int v25; // esi
  unsigned int v26; // r12d
  unsigned int i; // r14d
  unsigned int *v28; // rax
  unsigned int v29; // ecx
  unsigned int v30; // edx
  char *v31; // r13
  unsigned int v32; // edx
  CPort *PortFromPortId; // rax
  unsigned int v34; // r9d
  int v35; // edx
  unsigned __int8 *v36; // rdx
  int v37; // r9d
  int v38; // r9d
  unsigned int v39; // edx
  unsigned int WdiSetAddCipherKeysToIhv; // eax
  struct CPort *v41; // r14
  __int64 v42; // rax
  CPropertyCache *PortPropertyCache; // rax
  CPropertyCache *v44; // rax
  int v45; // edx
  __int128 v46; // xmm1
  int v47; // eax
  int *v49; // rax
  int v50; // edx
  int v51; // r8d
  int v52; // [rsp+20h] [rbp-B1h]
  char v53[8]; // [rsp+38h] [rbp-99h]
  char v54; // [rsp+38h] [rbp-99h]
  int v55; // [rsp+40h] [rbp-91h]
  int v56; // [rsp+48h] [rbp-89h]
  __int64 v57; // [rsp+70h] [rbp-61h]
  unsigned __int8 *v58[2]; // [rsp+78h] [rbp-59h] BYREF
  unsigned int v59; // [rsp+88h] [rbp-49h] BYREF
  _WDI_SET_ADD_CIPHER_KEYS_CONTAINER *v60; // [rsp+90h] [rbp-41h]
  char v61; // [rsp+98h] [rbp-39h]
  _OWORD v62[2]; // [rsp+A0h] [rbp-31h] BYREF
  int v63; // [rsp+C0h] [rbp-11h]
  unsigned int KeyTypeFromKeyIndex; // [rsp+120h] [rbp+4Fh] BYREF

  v59 = 0;
  v10 = a3;
  v60 = 0;
  v61 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      300,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  v12 = *((_DWORD *)this + 280);
  if ( !v12 || v10 < v12 || (v13 = (_DWORD *)*((_QWORD *)this + 139)) == 0 || !*v13 && !v13[1] )
  {
    PropertyList = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v49 = (int *)*((_QWORD *)this + 139);
      if ( v49 )
      {
        v50 = *v49;
        v51 = v49[1];
      }
      else
      {
        v50 = 0;
        v51 = 0;
      }
      WPP_RECORDER_SF_qDddqdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v50,
        v51,
        (_DWORD)a4,
        v52,
        (char)this,
        *((_DWORD *)this + 4),
        v12,
        v10,
        (char)v49,
        v50,
        v51);
    }
LABEL_57:
    if ( v60 )
      _WDI_SET_ADD_CIPHER_KEYS_CONTAINER::`vector deleting destructor'(v60, 3u);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      *(_DWORD *)v53 = PropertyList;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        a3,
        310,
        (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        *(_QWORD *)v53);
    }
    goto LABEL_63;
  }
  v14 = a5;
  *a4 = v12;
  *v14 = *((_DWORD *)this + 280);
  v15 = (unsigned int *)*((_QWORD *)this + 139);
  v16 = *v15;
  if ( !*v15 )
  {
LABEL_22:
    v25 = 0;
    v26 = 0;
    for ( i = 0; ; ++i )
    {
      v28 = (unsigned int *)*((_QWORD *)this + 139);
      v29 = v28[1];
      v30 = *v28;
      if ( i >= v29 + *v28 )
        break;
      v57 = 73LL * i;
      v31 = (char *)v15 + v57;
      KeyTypeFromKeyIndex = CSetDefaultKeyHelpers::GetKeyTypeFromKeyIndex(*(unsigned int *)((char *)v15 + v57 + 13));
      if ( !KeyTypeFromKeyIndex )
      {
        PropertyList = -1073676267;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_57;
        v37 = 303;
        v56 = *(_DWORD *)(v31 + 13);
        v55 = *(_DWORD *)(v31 + 17);
        v54 = i;
LABEL_40:
        LOBYTE(v32) = 2;
        WPP_RECORDER_SF_qDddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v32,
          a3,
          v37,
          (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v54,
          v55,
          v56);
        goto LABEL_57;
      }
      PortFromPortId = CAdapter::GetPortFromPortId(*((CAdapter **)this + 67), *((_WORD *)this + 26));
      if ( PortFromPortId && v34 == 3 )
      {
        CPort::AddCurrentConnectionFlag(PortFromPortId, v32);
        v34 = KeyTypeFromKeyIndex;
      }
      if ( v31[27] )
      {
        ++v26;
      }
      else
      {
        if ( v25 >= **((_DWORD **)this + 139) )
        {
          PropertyList = -1073741811;
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_57;
          LOBYTE(v56) = **((_DWORD **)this + 139);
          v37 = 304;
          LOBYTE(v55) = i;
          v54 = v25;
          goto LABEL_40;
        }
        v58[0] = (unsigned __int8 *)(264LL * v25);
        PropertyList = CSetDefaultKeyHelpers::FillSetCipherKeyParameters(v34, v31 + 9, &v58[0][(unsigned __int64)v60]);
        if ( PropertyList )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v35) = 2;
            WPP_RECORDER_SF_qDdd(
              WPP_GLOBAL_Control->DeviceExtension,
              v35,
              a3,
              305,
              (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
              (char)this,
              *((_DWORD *)this + 4),
              v25,
              i);
          }
          goto LABEL_57;
        }
        v36 = v58[0];
        a3 = 73 * i;
        *(_DWORD *)&v58[0][(unsigned __int64)v60 + 256] = *((unsigned __int8 *)v15 + v57 + 8);
        *(_DWORD *)((char *)v60 + (_QWORD)v36) |= 0x800u;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v36) = 4;
          WPP_RECORDER_SF_qDdddddd(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v36,
            v57,
            306,
            (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            v25,
            i,
            *((_BYTE *)v15 + v57 + 8),
            KeyTypeFromKeyIndex,
            *(_DWORD *)(v31 + 17),
            *(_DWORD *)(v31 + 13));
        }
        ++v25;
      }
    }
    if ( v25 < v30 || v26 < v29 )
    {
      PropertyList = -1073741811;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v30) = 2;
        WPP_RECORDER_SF_qDdddd(
          WPP_GLOBAL_Control->DeviceExtension,
          v30,
          a3,
          307,
          (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          v25,
          *v28,
          v26,
          v29);
      }
    }
    else
    {
      v38 = (int)a8;
      v39 = a6;
      *a7 = 29;
      WdiSetAddCipherKeysToIhv = GenerateWdiSetAddCipherKeysToIhv(
                                   (unsigned int)&v59,
                                   v39,
                                   (unsigned int)*((_QWORD *)this + 67) + 5384,
                                   v38,
                                   (__int64)a9);
      PropertyList = WdiSetAddCipherKeysToIhv;
      if ( WdiSetAddCipherKeysToIhv )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          *(_DWORD *)v53 = WdiSetAddCipherKeysToIhv;
          WPP_RECORDER_SF_qDD(
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            a3,
            308,
            (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            *(_QWORD *)v53);
        }
      }
      else
      {
        v41 = CAdapter::GetPortFromPortId(*((CAdapter **)this + 67), *((_WORD *)this + 26));
        v42 = *((_QWORD *)v41 + 9);
        if ( v42 && *(_BYTE *)(v42 + 1) )
        {
          *(_QWORD *)(*((_QWORD *)v41 + 9) + 120LL) = CSystem::get_CurrentTime();
          CPort::TraceLoggingRoamFinished(v41, 0);
        }
        if ( v25 )
        {
          *((_BYTE *)v41 + 432) = 1;
          PortPropertyCache = COidJobBase::GetPortPropertyCache(this);
          if ( CPropertyCache::GetPropertyBooleanOrDefault(PortPropertyCache, 0x14u, 0) )
          {
            KeyTypeFromKeyIndex = 0;
            *(_OWORD *)v58 = 0;
            v44 = COidJobBase::GetPortPropertyCache(this);
            PropertyList = CPropertyCache::GetPropertyList(
                             v44,
                             5u,
                             &KeyTypeFromKeyIndex,
                             (unsigned __int16 *)v58,
                             &v58[1]);
            if ( !PropertyList )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v45) = 4;
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v45,
                  PropertyList + 1,
                  309,
                  (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids);
              }
              v46 = *((_OWORD *)v58[1] + 1);
              v47 = *((_DWORD *)v58[1] + 8);
              v62[0] = *(_OWORD *)v58[1];
              v62[1] = v46;
              v63 = v47;
              CPort::UnBlockSSIDFor11r(v41, v62);
            }
          }
        }
      }
    }
    goto LABEL_57;
  }
  v17 = v16;
  v19 = v16;
  v18 = 264LL * v16;
  if ( !is_mul_ok(v19, 0x108u) )
    v18 = -1;
  v20 = __CFADD__(v18, 8);
  v21 = v18 + 8;
  if ( v20 )
    v21 = -1;
  v22 = operator new(v21);
  if ( v22 )
  {
    v23 = (_WDI_SET_ADD_CIPHER_KEYS_CONTAINER *)(v22 + 1);
    *v22 = v17;
    `vector constructor iterator'(
      v22 + 1,
      0x108u,
      (unsigned int)v17,
      (void *(*)(void *))_WDI_SET_ADD_CIPHER_KEYS_CONTAINER::_WDI_SET_ADD_CIPHER_KEYS_CONTAINER);
    v60 = v23;
  }
  else
  {
    v60 = 0;
  }
  if ( v60 )
  {
    v15 = (unsigned int *)*((_QWORD *)this + 139);
    v59 = *v15;
    goto LABEL_22;
  }
  PropertyList = -1073741670;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      a3,
      302,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      **((_DWORD **)this + 139));
    goto LABEL_57;
  }
LABEL_63:
  ArrayOfElements<_WDI_SET_ADD_CIPHER_KEYS_CONTAINER>::Cleanup(&v59);
  return PropertyList;
}

```

## disassembly

```asm
0x140078d60  push    rbp
0x140078d62  push    rbx
0x140078d63  push    rsi
0x140078d64  push    rdi
0x140078d65  push    r12
0x140078d67  push    r13
0x140078d69  push    r14
0x140078d6b  push    r15
0x140078d6d  lea     rbp, [rsp-7]
0x140078d72  sub     rsp, 0D8h
0x140078d79  xor     r13d, r13d
0x140078d7c  mov     rbx, r9
0x140078d7f  mov     [rbp+3Fh+var_88], r13d
0x140078d83  mov     esi, r8d
0x140078d86  mov     [rbp+3Fh+var_80], r13
0x140078d8a  mov     rdi, rcx
0x140078d8d  mov     [rbp+3Fh+var_78], r13b
0x140078d91  lea     r14, WPP_RECORDER_INITIALIZED
0x140078d98  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140078d9f  lea     r12, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140078da6  jz      short loc_140078DDE
0x140078da8  mov     rcx, cs:WPP_GLOBAL_Control
0x140078daf  cmp     byte ptr [rcx+29h], 5
0x140078db3  jnb     short loc_140078DBC
0x140078db5  cmp     [rcx+48h], r13w
0x140078dba  jz      short loc_140078DDE
0x140078dbc  mov     eax, [rdi+10h]
0x140078dbf  mov     r9d, 12Ch
0x140078dc5  mov     rcx, [rcx+40h]
0x140078dc9  mov     dl, 5
0x140078dcb  mov     [rsp+110h+var_E0], eax
0x140078dcf  mov     [rsp+110h+var_E8], rdi
0x140078dd4  mov     [rsp+110h+var_F0], r12
0x140078dd9  call    WPP_RECORDER_SF_qD
0x140078dde  mov     ecx, [rdi+460h]
0x140078de4  test    ecx, ecx
0x140078de6  jz      loc_1400793A0
0x140078dec  cmp     esi, ecx
0x140078dee  jb      loc_1400793A0
0x140078df4  mov     rax, [rdi+458h]
0x140078dfb  test    rax, rax
0x140078dfe  jz      loc_1400793A0
0x140078e04  cmp     [rax], r13d
0x140078e07  jnz     short loc_140078E13
0x140078e09  cmp     [rax+4], r13d
0x140078e0d  jz      loc_1400793A0
0x140078e13  mov     rax, [rbp+3Fh+arg_20]
0x140078e17  mov     [rbx], ecx
0x140078e19  mov     ecx, [rdi+460h]
0x140078e1f  mov     [rax], ecx
0x140078e21  mov     r15, [rdi+458h]
0x140078e28  mov     eax, [r15]
0x140078e2b  test    eax, eax
0x140078e2d  jz      loc_140078EE7
0x140078e33  mov     esi, eax
0x140078e35  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140078e3c  mov     r15d, 108h
0x140078e42  mov     eax, r15d
0x140078e45  mul     rsi
0x140078e48  cmovb   rax, rcx
0x140078e4c  add     rax, 8
0x140078e50  cmovb   rax, rcx
0x140078e54  mov     rcx, rax; unsigned __int64
0x140078e57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140078e5c  test    rax, rax
0x140078e5f  jz      short loc_140078E83
0x140078e61  lea     rbx, [rax+8]
0x140078e65  mov     [rax], rsi
0x140078e68  mov     rcx, rbx; void *
0x140078e6b  lea     r9, ??0_WDI_SET_ADD_CIPHER_KEYS_CONTAINER@@QEAA@XZ; void *(*)(void *)
0x140078e72  mov     r8d, esi; unsigned __int64
0x140078e75  mov     edx, r15d; unsigned __int64
0x140078e78  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x140078e7d  mov     [rbp+3Fh+var_80], rbx
0x140078e81  jmp     short loc_140078E87
0x140078e83  mov     [rbp+3Fh+var_80], r13
0x140078e87  cmp     [rbp+3Fh+var_80], r13
0x140078e8b  jnz     short loc_140078EDA
0x140078e8d  mov     ebx, 0C000009Ah
0x140078e92  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140078e99  jz      loc_140079321
0x140078e9f  mov     rax, [rdi+458h]
0x140078ea6  mov     r9d, 12Eh
0x140078eac  mov     rcx, cs:WPP_GLOBAL_Control
0x140078eb3  mov     dl, 2
0x140078eb5  mov     eax, [rax]
0x140078eb7  mov     rcx, [rcx+40h]
0x140078ebb  mov     dword ptr [rsp+110h+var_D8], eax
0x140078ebf  mov     eax, [rdi+10h]
0x140078ec2  mov     [rsp+110h+var_E0], eax
0x140078ec6  mov     [rsp+110h+var_E8], rdi
0x140078ecb  mov     [rsp+110h+var_F0], r12
0x140078ed0  call    WPP_RECORDER_SF_qDD
0x140078ed5  jmp     loc_1400792CA
0x140078eda  mov     r15, [rdi+458h]
0x140078ee1  mov     eax, [r15]
0x140078ee4  mov     [rbp+3Fh+var_88], eax
0x140078ee7  mov     esi, r13d
0x140078eea  mov     r12d, r13d
0x140078eed  mov     r14d, r13d
0x140078ef0  mov     rax, [rdi+458h]
0x140078ef7  mov     ecx, [rax+4]
0x140078efa  mov     edx, [rax]
0x140078efc  lea     eax, [rcx+rdx]
0x140078eff  cmp     r14d, eax
0x140078f02  jnb     loc_14007911D
0x140078f08  mov     eax, r14d
0x140078f0b  imul    rax, 49h ; 'I'
0x140078f0f  mov     [rbp+3Fh+var_A0], rax
0x140078f13  lea     r13, [rax+r15]
0x140078f17  mov     ecx, [r13+0Dh]
0x140078f1b  call    ?GetKeyTypeFromKeyIndex@CSetDefaultKeyHelpers@@SA?AW4_WDI_CIPHER_KEY_TYPE@@K@Z; CSetDefaultKeyHelpers::GetKeyTypeFromKeyIndex(ulong)
0x140078f20  mov     [rbp+3Fh+arg_0], eax
0x140078f23  mov     r9d, eax
0x140078f26  test    eax, eax
0x140078f28  jz      loc_1400790E7
0x140078f2e  movzx   edx, word ptr [rdi+34h]; unsigned __int16
0x140078f32  mov     rcx, [rdi+218h]; this
0x140078f39  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x140078f3e  test    rax, rax
0x140078f41  jz      short loc_140078F55
0x140078f43  cmp     r9d, 3
0x140078f47  jnz     short loc_140078F55
0x140078f49  mov     rcx, rax; this
0x140078f4c  call    ?AddCurrentConnectionFlag@CPort@@QEAAXK@Z; CPort::AddCurrentConnectionFlag(ulong)
0x140078f51  mov     r9d, [rbp+3Fh+arg_0]
0x140078f55  cmp     byte ptr [r13+1Bh], 0
0x140078f5a  jnz     loc_14007902B
0x140078f60  mov     rax, [rdi+458h]
0x140078f67  mov     ecx, [rax]
0x140078f69  cmp     esi, ecx
0x140078f6b  jnb     loc_140079085
0x140078f71  mov     r8, [rbp+3Fh+var_80]
0x140078f75  lea     rdx, [r13+9]
0x140078f79  mov     eax, esi
0x140078f7b  imul    rcx, rax, 108h
0x140078f82  mov     [rbp+3Fh+var_98], rcx
0x140078f86  add     r8, rcx
0x140078f89  mov     ecx, r9d
0x140078f8c  call    ?FillSetCipherKeyParameters@CSetDefaultKeyHelpers@@SAHW4_WDI_CIPHER_KEY_TYPE@@PEAUDOT11_CIPHER_DEFAULT_KEY_VALUE@@PEAU_WDI_SET_ADD_CIPHER_KEYS_CONTAINER@@@Z; CSetDefaultKeyHelpers::FillSetCipherKeyParameters(_WDI_CIPHER_KEY_TYPE,DOT11_CIPHER_DEFAULT_KEY_VALUE *,_WDI_SET_ADD_CIPHER_KEYS_CONTAINER *)
0x140078f91  mov     ebx, eax
0x140078f93  test    eax, eax
0x140078f95  jnz     loc_140079036
0x140078f9b  mov     rax, [rbp+3Fh+var_80]
0x140078f9f  mov     rdx, [rbp+3Fh+var_98]
0x140078fa3  mov     r8, [rbp+3Fh+var_A0]
0x140078fa7  movzx   ecx, byte ptr [r8+r15+8]
0x140078fad  mov     [rdx+rax+100h], ecx
0x140078fb4  mov     rax, [rbp+3Fh+var_80]
0x140078fb8  bts     dword ptr [rdx+rax], 0Bh
0x140078fbd  lea     rax, WPP_RECORDER_INITIALIZED
0x140078fc4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140078fcb  jz      short loc_140079027
0x140078fcd  mov     eax, [r13+0Dh]
0x140078fd1  mov     r9d, 132h
0x140078fd7  movzx   ecx, byte ptr [r8+r15+8]
0x140078fdd  mov     dl, 4
0x140078fdf  mov     [rsp+110h+var_B0], eax
0x140078fe3  mov     eax, [r13+11h]
0x140078fe7  mov     [rsp+110h+var_B8], eax
0x140078feb  mov     eax, [rbp+3Fh+arg_0]
0x140078fee  mov     [rsp+110h+var_C0], eax
0x140078ff2  mov     eax, [rdi+10h]
0x140078ff5  mov     dword ptr [rsp+110h+var_C8], ecx
0x140078ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x140079000  mov     [rsp+110h+var_D0], r14d
0x140079005  mov     dword ptr [rsp+110h+var_D8], esi
0x140079009  mov     [rsp+110h+var_E0], eax
0x14007900d  lea     rax, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079014  mov     rcx, [rcx+40h]
0x140079018  mov     [rsp+110h+var_E8], rdi
0x14007901d  mov     [rsp+110h+var_F0], rax
0x140079022  call    WPP_RECORDER_SF_qDdddddd
0x140079027  inc     esi
0x140079029  jmp     short loc_14007902E
0x14007902b  inc     r12d
0x14007902e  inc     r14d
0x140079031  jmp     loc_140078EF0
0x140079036  lea     rax, WPP_RECORDER_INITIALIZED
0x14007903d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140079044  jz      loc_1400792BC
0x14007904a  mov     rcx, cs:WPP_GLOBAL_Control
0x140079051  lea     r12, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079058  mov     eax, [rdi+10h]
0x14007905b  mov     r9d, 131h
0x140079061  mov     [rsp+110h+var_D0], r14d
0x140079066  mov     dl, 2
0x140079068  mov     dword ptr [rsp+110h+var_D8], esi
0x14007906c  mov     rcx, [rcx+40h]
0x140079070  mov     [rsp+110h+var_E0], eax
0x140079074  mov     [rsp+110h+var_E8], rdi
0x140079079  mov     [rsp+110h+var_F0], r12
0x14007907e  call    WPP_RECORDER_SF_qDdd
0x140079083  jmp     short loc_1400790DB
0x140079085  mov     ebx, 0C000000Dh
0x14007908a  lea     rax, WPP_RECORDER_INITIALIZED
0x140079091  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140079098  jz      loc_1400792BC
0x14007909e  mov     dword ptr [rsp+110h+var_C8], ecx
0x1400790a2  mov     r9d, 130h
0x1400790a8  mov     [rsp+110h+var_D0], r14d
0x1400790ad  mov     dword ptr [rsp+110h+var_D8], esi
0x1400790b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400790b8  lea     r12, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x1400790bf  mov     eax, [rdi+10h]
0x1400790c2  mov     dl, 2
0x1400790c4  mov     [rsp+110h+var_E0], eax
0x1400790c8  mov     [rsp+110h+var_E8], rdi
0x1400790cd  mov     rcx, [rcx+40h]
0x1400790d1  mov     [rsp+110h+var_F0], r12
0x1400790d6  call    WPP_RECORDER_SF_qDddd
0x1400790db  lea     r14, WPP_RECORDER_INITIALIZED
0x1400790e2  jmp     loc_1400792CA
0x1400790e7  mov     ebx, 0C0010015h
0x1400790ec  lea     rax, WPP_RECORDER_INITIALIZED
0x1400790f3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400790fa  jz      loc_1400792BC
0x140079100  mov     eax, [r13+0Dh]
0x140079104  mov     r9d, 12Fh
0x14007910a  mov     dword ptr [rsp+110h+var_C8], eax
0x14007910e  mov     eax, [r13+11h]
0x140079112  mov     [rsp+110h+var_D0], eax
0x140079116  mov     dword ptr [rsp+110h+var_D8], r14d
0x14007911b  jmp     short loc_1400790B1
0x14007911d  cmp     esi, edx
0x14007911f  jb      loc_140079341
0x140079125  cmp     r12d, ecx
0x140079128  jb      loc_140079341
0x14007912e  mov     rax, [rbp+3Fh+arg_30]
0x140079132  lea     rcx, [rbp+3Fh+var_88]
0x140079136  mov     r9, [rbp+3Fh+arg_38]
0x14007913d  mov     edx, [rbp+3Fh+arg_28]
0x140079140  mov     dword ptr [rax], 1Dh
0x140079146  mov     r8, [rdi+218h]
0x14007914d  mov     rax, [rbp+3Fh+arg_40]
0x140079154  add     r8, 1508h
0x14007915b  mov     [rsp+110h+var_F0], rax
0x140079160  call    GenerateWdiSetAddCipherKeysToIhv
0x140079165  xor     r13d, r13d
0x140079168  mov     ebx, eax
0x14007916a  test    eax, eax
0x14007916c  jz      short loc_1400791BB
0x14007916e  lea     r14, WPP_RECORDER_INITIALIZED
0x140079175  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14007917c  jz      loc_1400792C3
0x140079182  mov     rcx, cs:WPP_GLOBAL_Control
0x140079189  lea     r12, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079190  mov     dword ptr [rsp+110h+var_D8], eax
0x140079194  mov     r9d, 134h
0x14007919a  mov     eax, [rdi+10h]
0x14007919d  mov     dl, 2
0x14007919f  mov     [rsp+110h+var_E0], eax
0x1400791a3  mov     rcx, [rcx+40h]
0x1400791a7  mov     [rsp+110h+var_E8], rdi
0x1400791ac  mov     [rsp+110h+var_F0], r12
0x1400791b1  call    WPP_RECORDER_SF_qDD
0x1400791b6  jmp     loc_1400792CA
0x1400791bb  movzx   edx, word ptr [rdi+34h]; unsigned __int16
0x1400791bf  mov     rcx, [rdi+218h]; this
0x1400791c6  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x1400791cb  mov     r14, rax
0x1400791ce  mov     rax, [rax+48h]
0x1400791d2  test    rax, rax
0x1400791d5  jz      short loc_1400791F4
0x1400791d7  cmp     [rax+1], r13b
0x1400791db  jz      short loc_1400791F4
0x1400791dd  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400791e2  mov     rcx, [r14+48h]
0x1400791e6  xor     edx, edx; int
0x1400791e8  mov     [rcx+78h], rax
0x1400791ec  mov     rcx, r14; this
0x1400791ef  call    ?TraceLoggingRoamFinished@CPort@@QEAAXH@Z; CPort::TraceLoggingRoamFinished(int)
0x1400791f4  test    esi, esi
0x1400791f6  jz      loc_1400792BC
0x1400791fc  mov     rcx, rdi; this
0x1400791ff  mov     byte ptr [r14+1B0h], 1
0x140079207  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x14007920c  xor     r8d, r8d; unsigned __int8
0x14007920f  mov     rcx, rax; this
0x140079212  lea     edx, [r8+14h]; unsigned int
0x140079216  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14007921b  test    al, al
0x14007921d  jz      loc_1400792BC
0x140079223  xorps   xmm0, xmm0
0x140079226  mov     [rbp+3Fh+arg_0], r13d
0x14007922a  mov     rcx, rdi; this
0x14007922d  movups  xmmword ptr [rbp+3Fh+var_98], xmm0
0x140079231  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x140079236  lea     rcx, [rbp+3Fh+var_98+8]
0x14007923a  mov     edx, 5; unsigned int
0x14007923f  mov     [rsp+110h+var_F0], rcx; unsigned __int8 **
0x140079244  lea     r9, [rbp+3Fh+var_98]; unsigned __int16 *
0x140079248  mov     rcx, rax; this
0x14007924b  lea     r8, [rbp+3Fh+arg_0]; unsigned int *
0x14007924f  call    ?GetPropertyList@CPropertyCache@@QEBAHKPEAKPEAGPEAPEAE@Z; CPropertyCache::GetPropertyList(ulong,ulong *,ushort *,uchar * *)
0x140079254  mov     ebx, eax
0x140079256  test    eax, eax
0x140079258  jnz     short loc_1400792BC
0x14007925a  lea     rax, WPP_RECORDER_INITIALIZED
0x140079261  cmp     cs:WPP_RECORDER_INITIALIZED, rax
  ... truncated ...
```
