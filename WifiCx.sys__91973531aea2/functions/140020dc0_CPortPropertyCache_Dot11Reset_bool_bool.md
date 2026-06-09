# CPortPropertyCache::Dot11Reset(bool,bool)

- ea: `0x140020dc0`
- end: `0x1400218ea`
- name: `?Dot11Reset@CPortPropertyCache@@QEAAH_N0@Z`
- size: `2858`
- prototype: `__int64 __fastcall(CPortPropertyCache *__hidden this, bool, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x140020d0c`
- `0x140067578`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x14001a630`
- `0x140020dc0`
- `0x14002a9f8`
- `0x14002aaec`
- `0x1400593d0`
- `0x140066e70`
- `0x1400683ac`
- `0x140068404`
- `0x140068474`
- `0x1400685d4`
- `0x1400dfd00`

## pseudocode

```c
__int64 __fastcall CPortPropertyCache::Dot11Reset(CPortPropertyCache *this, char a2, unsigned __int8 a3)
{
  __int16 v3; // r14
  __int64 *v6; // rdx
  unsigned int PropertyBuffer; // ebx
  __int64 v8; // rsi
  int v9; // edx
  int v10; // edx
  int v11; // r8d
  const char *v12; // rax
  int v13; // edx
  int v14; // r9d
  __m128i *p_si128; // [rsp+28h] [rbp-B1h]
  __int16 v17; // [rsp+30h] [rbp-A9h]
  unsigned __int8 v18[4]; // [rsp+40h] [rbp-99h] BYREF
  unsigned __int8 v19[4]; // [rsp+44h] [rbp-95h] BYREF
  __int16 v20; // [rsp+48h] [rbp-91h]
  int v21; // [rsp+4Ch] [rbp-8Dh] BYREF
  unsigned __int8 v22[4]; // [rsp+50h] [rbp-89h] BYREF
  unsigned int v23; // [rsp+54h] [rbp-85h] BYREF
  _DWORD v24[2]; // [rsp+58h] [rbp-81h] BYREF
  unsigned __int8 *v25; // [rsp+60h] [rbp-79h] BYREF
  __m128i si128; // [rsp+68h] [rbp-71h] BYREF
  int v27; // [rsp+78h] [rbp-61h]
  __m128i v28; // [rsp+80h] [rbp-59h]
  __int64 v29; // [rsp+90h] [rbp-49h]
  unsigned __int8 v30[32]; // [rsp+98h] [rbp-41h] BYREF
  unsigned __int8 v31[16]; // [rsp+B8h] [rbp-21h] BYREF
  __int128 v32; // [rsp+C8h] [rbp-11h]
  __int64 v33; // [rsp+D8h] [rbp-1h]

  v3 = a3;
  *(_DWORD *)v18 = 6;
  v23 = 0;
  *(_OWORD *)v31 = 0;
  v25 = 0;
  v32 = 0;
  LODWORD(v33) = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  memset(v30, 0, 28);
  v28 = _mm_load_si128((const __m128i *)&_xmm);
  *(_DWORD *)v19 = -1;
  v20 = -1;
  *(_DWORD *)v22 = -1;
  v27 = 0;
  v24[0] = 8;
  v24[1] = 4;
  v21 = 9;
  v29 = 257;
  v6 = WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v6,
      1,
      80,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids);
    v6 = WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids;
  }
  if ( *((_DWORD *)this + 2) <= 1u )
  {
    PropertyBuffer = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_93;
    v8 = 0;
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v6,
      1,
      19,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      1);
  }
  else
  {
    PropertyBuffer = 0;
    v8 = *((_QWORD *)this + 2) + 56LL;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(p_si128) = PropertyBuffer;
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v6,
      1,
      22,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      p_si128);
  }
  if ( PropertyBuffer )
    goto LABEL_93;
  *(_DWORD *)v8 = 1;
  *(_DWORD *)(v8 + 4) = 1;
  *(_DWORD *)(v8 + 16) = 0;
  *(_BYTE *)(v8 + 8) = 1;
  PropertyBuffer = CPropertyCache::SetPropertyList(this, 5u, 0x24u, 1u, v31);
  if ( PropertyBuffer )
    goto LABEL_93;
  PropertyBuffer = CPropertyCache::SetPropertyBuffer(this, 6u, 0x1Cu, v30);
  if ( PropertyBuffer )
    goto LABEL_93;
  PropertyBuffer = CPropertyCache::SetPropertyList(this, 7u, 4u, 1u, v18);
  if ( PropertyBuffer )
    goto LABEL_93;
  *(_WORD *)v18 = 0;
  v33 = 0;
  v17 = 5;
  p_si128 = &si128;
  *(_OWORD *)v31 = 0;
  v32 = 0;
  CPortPropertyCache::AddCiphersToSupportedList(this, 0, v31, v18);
  PropertyBuffer = CPropertyCache::SetPropertyList(
                     this,
                     9u,
                     4 * *(unsigned __int16 *)v18,
                     *(unsigned __int16 *)v18,
                     v31);
  if ( PropertyBuffer )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return PropertyBuffer;
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      1,
      81,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids);
  }
  else
  {
    *(_WORD *)v18 = 0;
    v33 = 0;
    v17 = v3 + 5;
    *(_OWORD *)v31 = 0;
    v32 = 0;
    CPortPropertyCache::AddCiphersToSupportedList(this, 1, v31, v18);
    PropertyBuffer = CPropertyCache::SetPropertyList(
                       this,
                       8u,
                       4 * *(unsigned __int16 *)v18,
                       *(unsigned __int16 *)v18,
                       v31);
    if ( PropertyBuffer )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return PropertyBuffer;
      v12 = "mlo";
      if ( !(_BYTE)v3 )
        v12 = "non-mlo";
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        v11,
        82,
        (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
        (__int64)v12);
      goto LABEL_93;
    }
    *(_WORD *)v18 = 0;
    v33 = 0;
    v17 = 2;
    p_si128 = (__m128i *)v24;
    *(_OWORD *)v31 = 0;
    v32 = 0;
    CPortPropertyCache::AddCiphersToSupportedList(this, 1, v31, v18);
    PropertyBuffer = CPropertyCache::SetPropertyList(
                       this,
                       0xAu,
                       4 * *(unsigned __int16 *)v18,
                       *(unsigned __int16 *)v18,
                       v31);
    if ( PropertyBuffer )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return PropertyBuffer;
      v14 = 83;
    }
    else
    {
      v17 = 1;
      v33 = 0;
      *(_WORD *)v18 = 0;
      p_si128 = (__m128i *)&v21;
      *(_OWORD *)v31 = 0;
      v32 = 0;
      CPortPropertyCache::AddCiphersToSupportedList(this, 1, v31, v18);
      PropertyBuffer = CPropertyCache::SetPropertyList(
                         this,
                         0xBu,
                         4 * *(unsigned __int16 *)v18,
                         *(unsigned __int16 *)v18,
                         v31);
      if ( !PropertyBuffer )
      {
        PropertyBuffer = CPropertyCache::SetPropertyList(this, 0x10u, 6u, 1u, v19);
        if ( !PropertyBuffer )
        {
          PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0xFu, 1u);
          if ( !PropertyBuffer )
          {
            PropertyBuffer = CPropertyCache::SetPropertyList(this, 0x2Au, 0, 0, 0);
            if ( !PropertyBuffer )
            {
              PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x2Bu, 0);
              if ( !PropertyBuffer )
              {
                PropertyBuffer = CPropertyCache::SetPropertyList(this, 0x2Cu, 0, 0, 0);
                if ( !PropertyBuffer )
                {
                  PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x2Fu, 0);
                  if ( !PropertyBuffer )
                  {
                    PropertyBuffer = CPropertyCache::SetPropertyULong(this, 0x2Du, 0);
                    if ( !PropertyBuffer )
                    {
                      PropertyBuffer = CPropertyCache::SetPropertyULong(this, 0x2Eu, 0);
                      if ( !PropertyBuffer )
                      {
                        PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x30u, 0);
                        if ( !PropertyBuffer )
                        {
                          PropertyBuffer = CPropertyCache::SetPropertyList(this, 0x31u, 4u, 1u, v22);
                          if ( !PropertyBuffer )
                          {
                            PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0xCu, 0);
                            if ( !PropertyBuffer )
                            {
                              PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0xDu, 0);
                              if ( !PropertyBuffer )
                              {
                                PropertyBuffer = CPropertyCache::SetPropertyBuffer(this, 0xEu, 0, 0);
                                if ( !PropertyBuffer )
                                {
                                  PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x1Eu, 0);
                                  if ( !PropertyBuffer )
                                  {
                                    PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x17u, 1u);
                                    if ( !PropertyBuffer )
                                    {
                                      PropertyBuffer = CPropertyCache::SetPropertyULong(this, 0x1Bu, 1u);
                                      if ( !PropertyBuffer )
                                      {
                                        PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x1Cu, 0);
                                        if ( !PropertyBuffer )
                                        {
                                          PropertyBuffer = CPropertyCache::SetPropertyULong(this, 0x33u, 0);
                                          if ( !PropertyBuffer )
                                          {
                                            PropertyBuffer = CPropertyCache::SetPropertyULong(this, 0x1Du, 2u);
                                            if ( !PropertyBuffer )
                                            {
                                              PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x1Fu, 0);
                                              if ( !PropertyBuffer )
                                              {
                                                PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x21u, 1u);
                                                if ( !PropertyBuffer )
                                                {
                                                  PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x20u, 0);
                                                  if ( !PropertyBuffer )
                                                  {
                                                    PropertyBuffer = CPropertyCache::SetPropertyULong(
                                                                       this,
                                                                       0x22u,
                                                                       0x92Bu);
                                                    if ( !PropertyBuffer )
                                                    {
                                                      PropertyBuffer = CPropertyCache::SetPropertyULong(
                                                                         this,
                                                                         0x23u,
                                                                         0x92Au);
                                                      if ( !PropertyBuffer )
                                                      {
                                                        PropertyBuffer = CPropertyCache::SetPropertyULong(
                                                                           this,
                                                                           0x25u,
                                                                           1u);
                                                        if ( !PropertyBuffer )
                                                        {
                                                          PropertyBuffer = CPropertyCache::SetPropertyULong(
                                                                             this,
                                                                             0x26u,
                                                                             0);
                                                          if ( !PropertyBuffer )
                                                          {
                                                            PropertyBuffer = CPropertyCache::SetPropertyULong(
                                                                               this,
                                                                               0x27u,
                                                                               0);
                                                            if ( !PropertyBuffer )
                                                            {
                                                              PropertyBuffer = CPropertyCache::SetPropertyBuffer(
                                                                                 this,
                                                                                 0x28u,
                                                                                 0,
                                                                                 0);
                                                              if ( !PropertyBuffer )
                                                              {
                                                                PropertyBuffer = CPropertyCache::SetPropertyULong(
                                                                                   this,
                                                                                   0x24u,
                                                                                   0x7D0u);
                                                                if ( !PropertyBuffer )
                                                                {
                                                                  PropertyBuffer = CPropertyCache::SetPropertyULong(
                                                                                     this,
                                                                                     0x42u,
                                                                                     0x64u);
                                                                  if ( !PropertyBuffer )
                                                                  {
                                                                    PropertyBuffer = CPropertyCache::SetPropertyULong(
                                                                                       this,
                                                                                       0x43u,
                                                                                       1u);
                                                                    if ( !PropertyBuffer )
                                                                    {
                                                                      PropertyBuffer = CPropertyCache::SetPropertyBoolean(
                                                                                         this,
                                                                                         0x45u,
                                                                                         0);
                                                                      if ( !PropertyBuffer )
                                                                      {
                                                                        PropertyBuffer = CPropertyCache::SetPropertyBoolean(
                                                                                           this,
                                                                                           0x46u,
                                                                                           0);
                                                                        if ( !PropertyBuffer
                                                                          && (!a2
                                                                           || (PropertyBuffer = CPropertyCache::SetPropertyULong(
                                                                                                  this,
                                                                                                  0x1Au,
                                                                                                  0)) == 0
                                                                           && (PropertyBuffer = CPropertyCache::SetPropertyList(
                                                                                                  this,
                                                                                                  0x29u,
                                                                                                  0,
                                                                                                  0,
                                                                                                  0)) == 0) )
                                                                        {
                                                                          PropertyBuffer = CPropertyCache::SetPropertyULong(
                                                                                             this,
                                                                                             2u,
                                                                                             0xFFFFFFFF);
                                                                          if ( !PropertyBuffer )
                                                                          {
                                                                            PropertyBuffer = CPropertyCache::SetPropertyULong(
                                                                                               this,
                                                                                               3u,
                                                                                               0xFFFFFFFF);
                                                                            if ( !PropertyBuffer )
                                                                            {
                                                                              PropertyBuffer = CPropertyCache::SetPropertyUchar(
                                                                                                 this,
                                                                                                 4u,
                                                                                                 0xFFu);
                                                                              if ( !PropertyBuffer )
                                                                              {
                                                                                PropertyBuffer = CPropertyCache::SetPropertyBuffer(
                                                                                                   this,
                                                                                                   0x16u,
                                                                                                   0,
                                                                                                   0);
                                                                                if ( !PropertyBuffer )
                                                                                {
                                                                                  PropertyBuffer = CPropertyCache::SetPropertyBuffer(
                                                                                                     this,
                                                                                                     0x41u,
                                                                                                     0,
                                                                                                     0);
                                                                                  if ( !PropertyBuffer )
                                                                                  {
                                                                                    PropertyBuffer = CPropertyCache::SetPropertyBuffer(this, 0x47u, 0, 0);
                                                                                    if ( !PropertyBuffer )
                                                                                    {
                                                                                      PropertyBuffer = CPropertyCache::SetPropertyULong(this, 0x34u, 0);
                                                                                      if ( !PropertyBuffer )
                                                                                      {
                                                                                        PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x52u, 0);
                                                                                        if ( !PropertyBuffer )
                                                                                        {
                                                                                          PropertyBuffer = CPropertyCache::SetPropertyULong(this, 0x54u, 0xFFFFu);
                                                                                          if ( !PropertyBuffer )
                                                                                          {
                                                                                            PropertyBuffer = CPropertyCache::SetPropertyBuffer(this, 0x11u, 0, 0);
                                                                                            if ( !PropertyBuffer )
                                                                                            {
                                                                                              PropertyBuffer = CPropertyCache::SetPropertyBuffer(this, 0x12u, 0, 0);
                                                                                              if ( !PropertyBuffer )
                                                                                              {
                                                                                                PropertyBuffer = CPropertyCache::SetPropertyBuffer(this, 0x13u, 0, 0);
                                                                                                if ( !PropertyBuffer )
                                                                                                {
                                                                                                  PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x14u, 0);
                                                                                                  if ( !PropertyBuffer )
                                                                                                  {
                                                                                                    PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x84u, 0);
                                                                                                    if ( !PropertyBuffer )
                                                                                                    {
                                                                                                      PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x85u, 0);
                                                                                                      if ( !PropertyBuffer )
                                                                                                      {
                                                                                                        PropertyBuffer = CPropertyCache::SetPropertyBuffer(this, 0x87u, 0, 0);
                                                                                                        if ( !PropertyBuffer )
                                                                                                        {
                                                                                                          PropertyBuffer = CPropertyCache::SetPropertyList(this, 0x88u, 0, 0, 0);
                                                                                                          if ( !PropertyBuffer )
                                                                                                          {
                                                                                                            PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x89u, 0);
                                                                                                            if ( !PropertyBuffer && (!(unsigned int)Feature_WiFiDirect2_Support__private_IsEnabledDeviceUsageNoInline() || (PropertyBuffer = CPropertyCache::SetPropertyBuffer(this, 0x8Au, 0, 0)) == 0 && (PropertyBuffer = CPropertyCache::SetPropertyBuffer(this, 0x8Bu, 0, 0)) == 0 && (PropertyBuffer = CPropertyCache::SetPropertyList(this, 0x8Cu, 0, 0, 0)) == 0) )
                                                                                                            {
                                                                                                              PropertyBuffer = CPropertyCache::GetPropertyBuffer(*((CPropertyCache **)this + 3), 0x19u, &v23, &v25);
                                                                                                              if ( !PropertyBuffer && *((_DWORD *)v25 + 77) != 1 )
                                                                                                                PropertyBuffer = CPropertyCache::SetPropertyBoolean(this, 0x21u, 0);
                                                                                                            }
                                                                                                          }
                                                                                                        }
                                                                                                      }
                                                                                                    }
                                                                                                  }
                                                                                                }
                                                                                              }
                                                                                            }
                                                                                          }
                                                                                        }
                                                                                      }
                                                                                    }
                                                                                  }
                                                                                }
                                                                              }
                                                                            }
                                                                          }
                                                                        }
                                                                      }
                                                                    }
                                                                  }
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        goto LABEL_93;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return PropertyBuffer;
      v14 = 84;
    }
    LOBYTE(v13) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      1,
      v14,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids);
  }
LABEL_93:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(p_si128) = PropertyBuffer;
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v6,
      1,
      85,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      p_si128,
      v17);
  }
  return PropertyBuffer;
}

```

## disassembly

```asm
0x140020dc0  push    rbp
0x140020dc2  push    rbx
0x140020dc3  push    rsi
0x140020dc4  push    rdi
0x140020dc5  push    r12
0x140020dc7  push    r13
0x140020dc9  push    r14
0x140020dcb  push    r15
0x140020dcd  lea     rbp, [rsp-1Fh]
0x140020dd2  sub     rsp, 0F8h
0x140020dd9  mov     rax, cs:__security_cookie
0x140020de0  xor     rax, rsp
0x140020de3  mov     [rbp+57h+var_50], rax
0x140020de7  xorps   xmm0, xmm0
0x140020dea  movzx   r14d, r8b
0x140020dee  xor     r12d, r12d
0x140020df1  mov     dword ptr [rsp+130h+var_F0], 6
0x140020df9  movups  xmmword ptr [rbp+57h+var_97], xmm0
0x140020dfd  xor     eax, eax
0x140020dff  mov     r15b, dl
0x140020e02  movups  xmmword ptr [rbp+57h+var_97+0Bh], xmm0
0x140020e06  mov     rdi, rcx
0x140020e09  mov     [rsp+130h+var_DC], r12d
0x140020e0e  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x140020e12  mov     [rbp+57h+var_D0], r12
0x140020e16  movups  [rbp+57h+var_68], xmm0
0x140020e1a  mov     dword ptr [rbp+57h+var_58], eax
0x140020e1d  movdqa  xmm0, cs:__xmm@00000101000000020000000400000008
0x140020e25  movdqu  [rbp+57h+var_C8], xmm0
0x140020e2a  mov     [rbp+57h+var_98], r12b
0x140020e2e  movdqa  xmm0, cs:__xmm@00000002000000040000000800000009
0x140020e36  movdqu  [rbp+57h+var_B0], xmm0
0x140020e3b  mov     dword ptr [rsp+130h+var_EC], 0FFFFFFFFh
0x140020e43  mov     [rsp+130h+var_E8], 0FFFFh
0x140020e4a  mov     dword ptr [rsp+130h+var_E0], 0FFFFFFFFh
0x140020e52  mov     [rbp+57h+var_B8], r12d
0x140020e56  mov     [rsp+130h+var_D8], 8
0x140020e5e  mov     [rbp+57h+var_D4], 4
0x140020e65  mov     [rsp+130h+var_E4], 9
0x140020e6d  mov     [rbp+57h+var_A0], 101h
0x140020e75  lea     rax, WPP_RECORDER_INITIALIZED
0x140020e7c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020e83  lea     r10d, [r12+5]
0x140020e88  lea     rdx, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x140020e8f  lea     r13d, [r12+1]
0x140020e94  jz      short loc_140020ED2
0x140020e96  mov     rcx, cs:WPP_GLOBAL_Control
0x140020e9d  cmp     [rcx+29h], r10b
0x140020ea1  jnb     short loc_140020EAA
0x140020ea3  cmp     [rcx+48h], r12w
0x140020ea8  jz      short loc_140020ED2
0x140020eaa  mov     rcx, [rcx+40h]
0x140020eae  mov     r9d, 50h ; 'P'
0x140020eb4  mov     [rsp+130h+var_110], rdx
0x140020eb9  mov     r8d, r13d
0x140020ebc  mov     dl, r10b
0x140020ebf  call    WPP_RECORDER_SF_
0x140020ec4  lea     rax, WPP_RECORDER_INITIALIZED
0x140020ecb  lea     rdx, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x140020ed2  cmp     [rdi+8], r13d
0x140020ed6  jbe     short loc_140020EE5
0x140020ed8  mov     rsi, [rdi+10h]
0x140020edc  mov     ebx, r12d
0x140020edf  add     rsi, 38h ; '8'
0x140020ee3  jmp     short loc_140020F26
0x140020ee5  mov     ebx, 0C000000Dh
0x140020eea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020ef1  jz      loc_14002187B
0x140020ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x140020efe  mov     r9d, 13h
0x140020f04  mov     dword ptr [rsp+130h+var_108], r13d
0x140020f09  mov     r8d, r13d
0x140020f0c  mov     [rsp+130h+var_110], rdx
0x140020f11  mov     rsi, r12
0x140020f14  mov     dl, 2
0x140020f16  mov     rcx, [rcx+40h]
0x140020f1a  call    WPP_RECORDER_SF_d
0x140020f1f  lea     rax, WPP_RECORDER_INITIALIZED
0x140020f26  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140020f2d  jz      short loc_140020F67
0x140020f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f36  cmp     byte ptr [rcx+29h], 5
0x140020f3a  jnb     short loc_140020F43
0x140020f3c  cmp     [rcx+48h], r12w
0x140020f41  jz      short loc_140020F67
0x140020f43  mov     rcx, [rcx+40h]
0x140020f47  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x140020f4e  mov     r9d, 16h
0x140020f54  mov     dword ptr [rsp+130h+var_108], ebx
0x140020f58  mov     r8d, r13d
0x140020f5b  mov     [rsp+130h+var_110], rax
0x140020f60  mov     dl, 5
0x140020f62  call    WPP_RECORDER_SF_d
0x140020f67  test    ebx, ebx
0x140020f69  jnz     loc_14002187B
0x140020f6f  mov     [rsi], r13d
0x140020f72  mov     [rsi+4], r13d
0x140020f76  mov     [rsi+10h], r12d
0x140020f7a  mov     [rsi+8], r13b
0x140020f7e  lea     rax, [rbp+57h+var_78]
0x140020f82  mov     r9d, r13d; unsigned __int16
0x140020f85  lea     edx, [rbx+5]; unsigned int
0x140020f88  mov     [rsp+130h+var_110], rax; unsigned __int8 *
0x140020f8d  lea     r8d, [rbx+24h]; unsigned int
0x140020f91  mov     rcx, rdi; this
0x140020f94  call    ?SetPropertyList@CPropertyCache@@QEAAHKKGPEAE@Z; CPropertyCache::SetPropertyList(ulong,ulong,ushort,uchar *)
0x140020f99  mov     ebx, eax
0x140020f9b  test    eax, eax
0x140020f9d  jnz     loc_14002187B
0x140020fa3  lea     r9, [rbp+57h+var_98]; unsigned __int8 *
0x140020fa7  mov     rcx, rdi; this
0x140020faa  lea     edx, [rax+6]; unsigned int
0x140020fad  lea     r8d, [rax+1Ch]; unsigned int
0x140020fb1  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEBE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar const *)
0x140020fb6  mov     ebx, eax
0x140020fb8  test    eax, eax
0x140020fba  jnz     loc_14002187B
0x140020fc0  lea     rax, [rsp+130h+var_F0]
0x140020fc5  mov     r9d, r13d; unsigned __int16
0x140020fc8  lea     edx, [rbx+7]; unsigned int
0x140020fcb  mov     [rsp+130h+var_110], rax; unsigned __int8 *
0x140020fd0  lea     r8d, [rbx+4]; unsigned int
0x140020fd4  mov     rcx, rdi; this
0x140020fd7  call    ?SetPropertyList@CPropertyCache@@QEAAHKKGPEAE@Z; CPropertyCache::SetPropertyList(ulong,ulong,ushort,uchar *)
0x140020fdc  mov     ebx, eax
0x140020fde  test    eax, eax
0x140020fe0  jnz     loc_14002187B
0x140020fe6  xor     eax, eax
0x140020fe8  mov     word ptr [rsp+130h+var_F0], r12w
0x140020fee  xorps   xmm0, xmm0
0x140020ff1  mov     [rbp+57h+var_58], rax
0x140020ff5  lea     rax, [rbp+57h+var_C8]
0x140020ff9  xor     edx, edx
0x140020ffb  lea     esi, [rbx+5]
0x140020ffe  mov     rcx, rdi
0x140021001  mov     [rsp+130h+var_100], si
0x140021006  lea     r9, [rsp+130h+var_F0]
0x14002100b  lea     r8, [rbp+57h+var_78]
0x14002100f  mov     [rsp+130h+var_108], rax
0x140021014  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x140021018  movups  [rbp+57h+var_68], xmm0
0x14002101c  call    ?AddCiphersToSupportedList@CPortPropertyCache@@QEAAXW4_WFC_ADAPTER_PROPERTY_NAME@@PEAW4_DOT11_CIPHER_ALGORITHM@@PEAGG1G@Z; CPortPropertyCache::AddCiphersToSupportedList(_WFC_ADAPTER_PROPERTY_NAME,_DOT11_CIPHER_ALGORITHM *,ushort *,ushort,_DOT11_CIPHER_ALGORITHM *,ushort)
0x140021021  movzx   r9d, word ptr [rsp+130h+var_F0]; unsigned __int16
0x140021027  lea     rax, [rbp+57h+var_78]
0x14002102b  mov     r8d, r9d
0x14002102e  mov     [rsp+130h+var_110], rax; unsigned __int8 *
0x140021033  shl     r8d, 2; unsigned int
0x140021037  lea     edx, [rbx+9]; unsigned int
0x14002103a  mov     rcx, rdi; this
0x14002103d  call    ?SetPropertyList@CPropertyCache@@QEAAHKKGPEAE@Z; CPropertyCache::SetPropertyList(ulong,ulong,ushort,uchar *)
0x140021042  mov     ebx, eax
0x140021044  test    eax, eax
0x140021046  jz      short loc_140021086
0x140021048  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002104f  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140021056  jz      loc_1400218C7
0x14002105c  mov     rcx, cs:WPP_GLOBAL_Control
0x140021063  lea     r9d, [rsi+4Ch]
0x140021067  lea     rsi, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14002106e  mov     r8d, r13d
0x140021071  mov     dl, 2
0x140021073  mov     [rsp+130h+var_110], rsi
0x140021078  mov     rcx, [rcx+40h]
0x14002107c  call    WPP_RECORDER_SF_
0x140021081  jmp     loc_140021889
0x140021086  xor     eax, eax
0x140021088  mov     word ptr [rsp+130h+var_F0], r12w
0x14002108e  mov     [rbp+57h+var_58], rax
0x140021092  lea     rdx, [rbp+57h+var_B0]
0x140021096  xorps   xmm0, xmm0
0x140021099  lea     ecx, [rsi+r14]
0x14002109d  mov     [rsp+130h+var_100], cx
0x1400210a2  lea     rax, [rbp+57h+var_C8]
0x1400210a6  test    r14b, r14b
0x1400210a9  lea     r9, [rsp+130h+var_F0]
0x1400210ae  lea     r8, [rbp+57h+var_78]
0x1400210b2  mov     rcx, rdi
0x1400210b5  cmovnz  rax, rdx
0x1400210b9  mov     edx, r13d
0x1400210bc  mov     [rsp+130h+var_108], rax
0x1400210c1  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x1400210c5  movups  [rbp+57h+var_68], xmm0
0x1400210c9  call    ?AddCiphersToSupportedList@CPortPropertyCache@@QEAAXW4_WFC_ADAPTER_PROPERTY_NAME@@PEAW4_DOT11_CIPHER_ALGORITHM@@PEAGG1G@Z; CPortPropertyCache::AddCiphersToSupportedList(_WFC_ADAPTER_PROPERTY_NAME,_DOT11_CIPHER_ALGORITHM *,ushort *,ushort,_DOT11_CIPHER_ALGORITHM *,ushort)
0x1400210ce  movzx   r9d, word ptr [rsp+130h+var_F0]; unsigned __int16
0x1400210d4  lea     rax, [rbp+57h+var_78]
0x1400210d8  mov     r8d, r9d
0x1400210db  mov     [rsp+130h+var_110], rax; unsigned __int8 *
0x1400210e0  shl     r8d, 2; unsigned int
0x1400210e4  mov     edx, 8; unsigned int
0x1400210e9  mov     rcx, rdi; this
0x1400210ec  call    ?SetPropertyList@CPropertyCache@@QEAAHKKGPEAE@Z; CPropertyCache::SetPropertyList(ulong,ulong,ushort,uchar *)
0x1400210f1  mov     ebx, eax
0x1400210f3  test    eax, eax
0x1400210f5  jz      short loc_14002114E
0x1400210f7  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400210fe  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140021105  jz      loc_1400218C7
0x14002110b  test    r14b, r14b
0x14002110e  lea     rcx, aNonMlo_0; "non-mlo"
0x140021115  lea     rax, aMlo; "mlo"
0x14002111c  mov     r9d, 52h ; 'R'
0x140021122  cmovz   rax, rcx
0x140021126  lea     rsi, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14002112d  mov     rcx, cs:WPP_GLOBAL_Control
0x140021134  mov     dl, 2
0x140021136  mov     [rsp+130h+var_108], rax
0x14002113b  mov     [rsp+130h+var_110], rsi
0x140021140  mov     rcx, [rcx+40h]
0x140021144  call    WPP_RECORDER_SF_s
0x140021149  jmp     loc_140021889
0x14002114e  xor     eax, eax
0x140021150  mov     word ptr [rsp+130h+var_F0], r12w
0x140021156  xorps   xmm0, xmm0
0x140021159  mov     [rbp+57h+var_58], rax
0x14002115d  lea     r9, [rsp+130h+var_F0]
0x140021162  mov     edx, r13d
0x140021165  lea     r8, [rbp+57h+var_78]
0x140021169  mov     rcx, rdi
0x14002116c  lea     esi, [rax+2]
0x14002116f  lea     rax, [rsp+130h+var_D8]
0x140021174  mov     [rsp+130h+var_100], si
0x140021179  mov     [rsp+130h+var_108], rax
0x14002117e  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x140021182  movups  [rbp+57h+var_68], xmm0
0x140021186  call    ?AddCiphersToSupportedList@CPortPropertyCache@@QEAAXW4_WFC_ADAPTER_PROPERTY_NAME@@PEAW4_DOT11_CIPHER_ALGORITHM@@PEAGG1G@Z; CPortPropertyCache::AddCiphersToSupportedList(_WFC_ADAPTER_PROPERTY_NAME,_DOT11_CIPHER_ALGORITHM *,ushort *,ushort,_DOT11_CIPHER_ALGORITHM *,ushort)
0x14002118b  movzx   r9d, word ptr [rsp+130h+var_F0]; unsigned __int16
0x140021191  lea     rax, [rbp+57h+var_78]
0x140021195  mov     r8d, r9d
0x140021198  mov     [rsp+130h+var_110], rax; unsigned __int8 *
0x14002119d  shl     r8d, 2; unsigned int
0x1400211a1  lea     edx, [rsi+8]; unsigned int
0x1400211a4  mov     rcx, rdi; this
0x1400211a7  call    ?SetPropertyList@CPropertyCache@@QEAAHKKGPEAE@Z; CPropertyCache::SetPropertyList(ulong,ulong,ushort,uchar *)
0x1400211ac  mov     ebx, eax
0x1400211ae  test    eax, eax
0x1400211b0  jz      short loc_1400211F1
0x1400211b2  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400211b9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400211c0  jz      loc_1400218C7
0x1400211c6  lea     r9d, [rsi+51h]
0x1400211ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400211d1  lea     rax, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x1400211d8  mov     r8d, r13d
0x1400211db  mov     [rsp+130h+var_110], rax
0x1400211e0  mov     dl, sil
0x1400211e3  mov     rcx, [rcx+40h]
0x1400211e7  call    WPP_RECORDER_SF_
0x1400211ec  jmp     loc_140021882
0x1400211f1  xor     eax, eax
0x1400211f3  mov     [rsp+130h+var_100], r13w
0x1400211f9  xorps   xmm0, xmm0
0x1400211fc  mov     [rbp+57h+var_58], rax
0x140021200  lea     rax, [rsp+130h+var_E4]
0x140021205  mov     word ptr [rsp+130h+var_F0], r12w
0x14002120b  lea     r9, [rsp+130h+var_F0]
0x140021210  mov     [rsp+130h+var_108], rax
0x140021215  lea     r8, [rbp+57h+var_78]
0x140021219  mov     edx, r13d
0x14002121c  mov     rcx, rdi
0x14002121f  movups  xmmword ptr [rbp+57h+var_78], xmm0
0x140021223  movups  [rbp+57h+var_68], xmm0
0x140021227  call    ?AddCiphersToSupportedList@CPortPropertyCache@@QEAAXW4_WFC_ADAPTER_PROPERTY_NAME@@PEAW4_DOT11_CIPHER_ALGORITHM@@PEAGG1G@Z; CPortPropertyCache::AddCiphersToSupportedList(_WFC_ADAPTER_PROPERTY_NAME,_DOT11_CIPHER_ALGORITHM *,ushort *,ushort,_DOT11_CIPHER_ALGORITHM *,ushort)
0x14002122c  movzx   r9d, word ptr [rsp+130h+var_F0]; unsigned __int16
0x140021232  lea     rax, [rbp+57h+var_78]
0x140021236  mov     r8d, r9d
0x140021239  mov     [rsp+130h+var_110], rax; unsigned __int8 *
0x14002123e  shl     r8d, 2; unsigned int
0x140021242  mov     edx, 0Bh; unsigned int
0x140021247  mov     rcx, rdi; this
0x14002124a  call    ?SetPropertyList@CPropertyCache@@QEAAHKKGPEAE@Z; CPropertyCache::SetPropertyList(ulong,ulong,ushort,uchar *)
0x14002124f  mov     ebx, eax
0x140021251  test    eax, eax
0x140021253  jz      short loc_140021274
0x140021255  lea     rdi, WPP_RECORDER_INITIALIZED
0x14002125c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140021263  jz      loc_1400218C7
0x140021269  mov     r9d, 54h ; 'T'
0x14002126f  jmp     loc_1400211CA
0x140021274  mov     edx, 10h; unsigned int
0x140021279  lea     rax, [rsp+130h+var_EC]
0x14002127e  mov     r9d, r13d; unsigned __int16
0x140021281  mov     [rsp+130h+var_110], rax; unsigned __int8 *
0x140021286  mov     rcx, rdi; this
0x140021289  lea     r8d, [rdx-0Ah]; unsigned int
0x14002128d  call    ?SetPropertyList@CPropertyCache@@QEAAHKKGPEAE@Z; CPropertyCache::SetPropertyList(ulong,ulong,ushort,uchar *)
0x140021292  mov     ebx, eax
0x140021294  test    eax, eax
0x140021296  jnz     loc_14002187B
0x14002129c  mov     r8b, r13b; unsigned __int8
0x14002129f  lea     edx, [rax+0Fh]; unsigned int
0x1400212a2  mov     rcx, rdi; this
0x1400212a5  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x1400212aa  mov     ebx, eax
0x1400212ac  test    eax, eax
0x1400212ae  jnz     loc_14002187B
0x1400212b4  xor     r9d, r9d; unsigned __int16
0x1400212b7  mov     [rsp+130h+var_110], r12; unsigned __int8 *
0x1400212bc  xor     r8d, r8d; unsigned int
0x1400212bf  lea     edx, [rax+2Ah]; unsigned int
0x1400212c2  mov     rcx, rdi; this
  ... truncated ...
```
