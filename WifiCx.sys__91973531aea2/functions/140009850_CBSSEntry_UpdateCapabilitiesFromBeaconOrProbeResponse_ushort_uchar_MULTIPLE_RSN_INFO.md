# CBSSEntry::UpdateCapabilitiesFromBeaconOrProbeResponse(ushort,uchar *,MULTIPLE_RSN_INFO &)

- ea: `0x140009850`
- end: `0x140009d58`
- name: `?UpdateCapabilitiesFromBeaconOrProbeResponse@CBSSEntry@@IEAAXGPEAEAEAUMULTIPLE_RSN_INFO@@@Z`
- size: `1288`
- prototype: `void __fastcall(CBSSEntry *__hidden this, unsigned __int16, unsigned __int8 *, struct MULTIPLE_RSN_INFO *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x140014f20`

## callees

- `0x1400096a0`
- `0x140009850`
- `0x140009d60`
- `0x14000a030`
- `0x14000a160`
- `0x14000a34c`
- `0x140024a20`
- `0x14003abf4`
- `0x14006b8ac`
- `0x1400996bc`

## pseudocode

```c
void __fastcall CBSSEntry::UpdateCapabilitiesFromBeaconOrProbeResponse(
        CBSSEntry *this,
        unsigned __int16 a2,
        unsigned __int8 *a3,
        struct MULTIPLE_RSN_INFO *a4)
{
  unsigned __int64 v6; // rdx
  __int64 v7; // r8
  char v8; // cl
  char *v9; // rbx
  char *v10; // r14
  char v11; // di
  unsigned __int64 v12; // xmm1_8
  __int128 v13; // xmm0
  __int64 v14; // rax
  char v15; // cl
  _BYTE *v16; // r15
  unsigned int v17; // ebx
  int v18; // eax
  int v19; // eax
  char v20; // al
  __int128 v21; // xmm6
  __int64 v22; // r8
  char v23; // cl
  __int64 v24; // r8
  __int64 i; // rax
  __int64 j; // rax
  int v27; // edx
  int v28; // r8d
  __int64 v29; // rdx
  __int16 v30; // ax
  int v31; // [rsp+28h] [rbp-99h]
  void *Src[3]; // [rsp+48h] [rbp-79h] BYREF
  char v33; // [rsp+60h] [rbp-61h] BYREF
  _BYTE v34[23]; // [rsp+61h] [rbp-60h]
  char v35; // [rsp+78h] [rbp-49h]
  _OWORD v36[3]; // [rsp+80h] [rbp-41h] BYREF
  _BYTE v37[23]; // [rsp+B1h] [rbp-10h]
  char v38; // [rsp+128h] [rbp+67h] BYREF
  unsigned __int8 v39; // [rsp+130h] [rbp+6Fh] BYREF
  char *v40; // [rsp+138h] [rbp+77h]

  *(_QWORD *)&v36[0] = a3 + 12;
  *((_QWORD *)&v36[0] + 1) = a2 - 12LL;
  Src[2] = *((void **)&v36[0] + 1);
  LOBYTE(Src[0]) = 1;
  Src[1] = a3 + 12;
  wlan::parsers::details::TlvWalker<wlan::parsers::TlvView<unsigned char,unsigned char>,0>::GetNextTlv(Src, &v33);
  v8 = v33;
  v9 = (char *)Src[2];
  v10 = (char *)Src[1];
  v11 = v35;
  while ( v11 )
  {
    if ( v8 == 127 )
    {
      v16 = *(_BYTE **)&v34[7];
      v17 = 8 * *(_DWORD *)&v34[15];
      if ( (unsigned int)(8 * *(_DWORD *)&v34[15]) <= 0x46 )
        LOBYTE(v18) = 0;
      else
        v18 = (*(unsigned __int8 *)(*(_QWORD *)&v34[7] + 8LL) >> 6) & 1;
      *((_BYTE *)this + 949) = v18;
      if ( (_BYTE)v18
        && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(v6) = 5;
        WPP_RECORDER_SF__MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          v7,
          273,
          (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
          (__int64)this + 32);
      }
      if ( v17 > 0x51 && (v16[10] & 2) != 0 )
        *((_DWORD *)this + 222) |= 0x80u;
      if ( v17 > 0x52 && (v16[10] & 4) != 0 )
        *((_DWORD *)this + 222) |= 0x100u;
      if ( v17 <= 0x55 )
        LOBYTE(v19) = 0;
      else
        v19 = ((unsigned __int8)v16[10] >> 5) & 1;
      *((_BYTE *)this + 950) = v19;
      if ( v17 <= 0x20 )
        v20 = 0;
      else
        v20 = v16[4] & 1;
      *((_BYTE *)this + 951) = v20;
      *((_BYTE *)this + 952) = v17 > 0x36 && (v16[6] & 0x40) != 0;
      break;
    }
    if ( !v9 )
      goto LABEL_5;
    v38 = 0;
    memcpy_s(&v38, 1u, v10, 1u);
    if ( v9 == (char *)1 )
      goto LABEL_5;
    v39 = 0;
    memcpy_s(&v39, 1u, v10 + 1, 1u);
    v6 = v39;
    v40 = v10 + 2;
    if ( (unsigned __int64)(v9 - 2) >= v39 )
    {
      v7 = (__int64)&v10[v39 + 2];
      *(_DWORD *)((char *)Src + 1) = *(_DWORD *)((char *)&v40 + 1);
      v14 = (__int64)&v9[-v39 - 2];
      *(_WORD *)((char *)Src + 5) = *(_WORD *)((char *)&v40 + 5);
      HIBYTE(Src[0]) = HIBYTE(v40);
      v15 = 1;
      LOBYTE(Src[0]) = (_BYTE)v10 + 2;
    }
    else
    {
      v14 = 0;
      v15 = 0;
      v7 = 0;
      memset(Src, 0, sizeof(Src));
      v6 = 0;
    }
    if ( v15 )
    {
      v8 = v38;
      v9 = (char *)v14;
      v10 = (char *)v7;
      Src[1] = Src[0];
      v12 = v6;
      Src[2] = (void *)v6;
      v11 = 1;
      v13 = *(_OWORD *)((char *)Src + 1);
    }
    else
    {
LABEL_5:
      v12 = 0;
      v8 = 0;
      memset(&v36[1], 0, 32);
      v11 = 0;
      v13 = *(_OWORD *)((char *)&v36[1] + 1);
    }
    *(_OWORD *)v37 = v13;
    *(_QWORD *)&v37[15] = v12;
    *(_OWORD *)v34 = *(_OWORD *)v37;
    *(_QWORD *)&v34[15] = v12;
  }
  v21 = v36[0];
  LOBYTE(Src[0]) = 1;
  *(_OWORD *)&Src[1] = v36[0];
  wlan::parsers::details::FindTlv_wlan::parsers::TlvView_unsigned_char_unsigned_char___wlan::parsers::details::FindVendorSpecificInformationElement_::_2_::_lambda_1___(
    &v33,
    Src,
    597323600);
  if ( v35 )
  {
    if ( 8 * *(_DWORD *)&v34[15] )
      v23 = **(_BYTE **)&v34[7] & 1;
    else
      v23 = 0;
    *((_BYTE *)this + 953) = v23;
  }
  if ( (*((_DWORD *)this + 222) & 0x10) != 0 )
  {
    LOBYTE(v22) = -12;
    wlan::parsers::InformationElementBlobView::FindInformationElement(v36, &v33, v22);
    if ( v35 && (unsigned int)(8 * *(_DWORD *)&v34[15]) > 5 && (**(_BYTE **)&v34[7] & 0x20) != 0 )
      *((_DWORD *)this + 222) |= 0x20u;
    LOBYTE(v24) = 1;
    wlan::parsers::InformationElementBlobView::FindInformationElement(v36, &v33, v24);
    if ( v35 )
    {
      for ( i = 0; (unsigned __int64)(unsigned int)i < *(_QWORD *)&v34[15]; i = (unsigned int)(i + 1) )
      {
        if ( *(_BYTE *)(i + *(_QWORD *)&v34[7]) == 0xFB )
        {
          *((_DWORD *)this + 222) |= 0x40u;
          break;
        }
      }
      if ( (*((_DWORD *)this + 222) & 0x40) == 0 )
      {
        LOBYTE(v22) = 50;
        wlan::parsers::InformationElementBlobView::FindInformationElement(v36, &v33, v22);
        if ( v35 )
        {
          for ( j = 0; (unsigned __int64)(unsigned int)j < *(_QWORD *)&v34[15]; j = (unsigned int)(j + 1) )
          {
            if ( *(_BYTE *)(j + *(_QWORD *)&v34[7]) == 0xFB )
            {
              *((_DWORD *)this + 222) |= 0x40u;
              break;
            }
          }
        }
      }
    }
  }
  LOBYTE(v22) = 107;
  *((_BYTE *)this + 44) = 0;
  LOBYTE(Src[0]) = 1;
  *(_OWORD *)&Src[1] = v21;
  wlan::parsers::details::FindTlv_wlan::parsers::TlvView_unsigned_char_unsigned_char___wlan::parsers::details::FindExtendedInformationElement_::_2_::_lambda_1___(
    &v33,
    Src,
    v22);
  if ( v35 )
  {
    if ( *(_QWORD *)&v34[15] < 0xBu )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = 2;
        WPP_RECORDER_SF_Ld(
          WPP_GLOBAL_Control->DeviceExtension,
          v27,
          v28,
          275,
          (__int64)WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids,
          v34[15],
          11);
      }
    }
    else
    {
      v29 = *(_QWORD *)&v34[7] + 4LL;
      *((_BYTE *)this + 44) = 1;
      *(_DWORD *)((char *)this + 38) = *(_DWORD *)v29;
      v30 = *(_WORD *)(v29 + 4);
      *((_DWORD *)this + 222) |= 0x400u;
      *((_WORD *)this + 21) = v30;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        WPP_RECORDER_SF__MAC__MAC_(WPP_GLOBAL_Control->DeviceExtension, v29, v28, 274, v31, (__int64)this + 32, v29);
      }
    }
  }
  if ( (unsigned int)Feature_53299205__private_IsEnabledDeviceUsageNoInline()
    && *((_QWORD *)a4 + 40)
    && *((_BYTE *)a4 + 328) )
  {
    *((_DWORD *)this + 222) |= 0x4000u;
  }
}

```

## disassembly

```asm
0x140009850  mov     rax, rsp
0x140009853  push    rbp
0x140009854  push    r12
0x140009856  push    r13
0x140009858  lea     rbp, [rax-5Fh]
0x14000985c  sub     rsp, 100h
0x140009863  mov     [rax+20h], rbx
0x140009867  add     r8, 0Ch
0x14000986b  mov     [rax-28h], rdi
0x14000986f  mov     r13, rcx
0x140009872  mov     [rax-30h], r14
0x140009876  lea     rcx, [rbp+57h+Src]
0x14000987a  movaps  xmmword ptr [rax-48h], xmm6
0x14000987e  mov     r12, r9
0x140009881  movzx   eax, dx
0x140009884  lea     rdx, [rbp+57h+var_B8]
0x140009888  add     rax, 0FFFFFFFFFFFFFFF4h
0x14000988c  mov     qword ptr [rbp+57h+var_98], r8
0x140009890  mov     qword ptr [rbp+57h+var_98+8], rax
0x140009894  mov     [rbp+57h+var_C0], rax
0x140009898  mov     byte ptr [rbp+57h+Src], 1
0x14000989c  mov     [rbp+57h+Src+8], r8
0x1400098a0  call    ?GetNextTlv@?$TlvWalker@V?$TlvView@EE@parsers@wlan@@$0A@@details@parsers@wlan@@QEAA?AV?$optional@V?$TlvView@EE@parsers@wlan@@@utl@@XZ; wlan::parsers::details::TlvWalker<wlan::parsers::TlvView<uchar,uchar>,0>::GetNextTlv(void)
0x1400098a5  movzx   ecx, [rbp+57h+var_B8]
0x1400098a9  mov     rbx, [rbp+57h+var_C0]
0x1400098ad  mov     r14, [rbp+57h+Src+8]
0x1400098b1  movzx   edi, [rbp+57h+var_A0]
0x1400098b5  mov     [rsp+0F8h], rsi
0x1400098bd  nop     dword ptr [rax]
0x1400098c0  test    dil, dil
0x1400098c3  jz      loc_140009B20
0x1400098c9  cmp     cl, 7Fh
0x1400098cc  jz      loc_1400099C7
0x1400098d2  test    rbx, rbx
0x1400098d5  jnz     short loc_1400098F0
0x1400098d7  xorps   xmm1, xmm1
0x1400098da  xor     cl, cl
0x1400098dc  movups  [rbp+57h+var_88], xmm1
0x1400098e0  xor     dil, dil
0x1400098e3  movups  [rbp+57h+var_78], xmm1
0x1400098e7  movups  xmm0, [rbp+57h+var_88+1]
0x1400098eb  jmp     loc_1400099AC
0x1400098f0  cmp     rbx, 1
0x1400098f4  jb      short loc_1400098D7
0x1400098f6  mov     r9d, 1; MaxCount
0x1400098fc  mov     [rbp+57h+arg_0], 0
0x140009900  mov     edx, r9d; DstSize
0x140009903  lea     rcx, [rbp+57h+arg_0]; void *
0x140009907  mov     r8, r14; Src
0x14000990a  call    memcpy_s
0x14000990f  lea     rdi, [rbx-1]
0x140009913  lea     rsi, [r14+1]
0x140009917  cmp     rdi, 1
0x14000991b  jb      short loc_1400098D7
0x14000991d  mov     r9d, 1; MaxCount
0x140009923  mov     [rbp+57h+arg_8], 0
0x140009927  mov     edx, r9d; DstSize
0x14000992a  lea     rcx, [rbp+57h+arg_8]; void *
0x14000992e  mov     r8, rsi; Src
0x140009931  call    memcpy_s
0x140009936  movzx   edx, [rbp+57h+arg_8]
0x14000993a  lea     rax, [rdi-1]
0x14000993e  inc     rsi
0x140009941  mov     [rbp+57h+arg_10], rsi
0x140009945  cmp     rax, rdx
0x140009948  jnb     short loc_140009960
0x14000994a  xor     eax, eax
0x14000994c  xorps   xmm0, xmm0
0x14000994f  xor     cl, cl
0x140009951  mov     [rbp+57h+var_C0], rax
0x140009955  xor     r8d, r8d
0x140009958  movups  xmmword ptr [rbp+57h+Src], xmm0
0x14000995c  xor     edx, edx
0x14000995e  jmp     short loc_140009982
0x140009960  mov     ecx, dword ptr [rbp+57h+arg_10+1]
0x140009963  lea     r8, [rdx+rsi]
0x140009967  mov     dword ptr [rbp+57h+Src+1], ecx
0x14000996a  sub     rax, rdx
0x14000996d  movzx   ecx, word ptr [rbp+57h+arg_10+5]
0x140009971  mov     word ptr [rbp+57h+Src+5], cx
0x140009975  movzx   ecx, byte ptr [rbp+57h+arg_10+7]
0x140009979  mov     byte ptr [rbp+57h+Src+7], cl
0x14000997c  mov     cl, 1
0x14000997e  mov     byte ptr [rbp+57h+Src], sil
0x140009982  test    cl, cl
0x140009984  jz      loc_1400098D7
0x14000998a  movzx   ecx, [rbp+57h+arg_0]
0x14000998e  mov     rbx, rax
0x140009991  mov     rax, [rbp+57h+Src]
0x140009995  mov     r14, r8
0x140009998  mov     [rbp+57h+Src+8], rax
0x14000999c  movq    xmm1, rdx
0x1400099a1  mov     [rbp+57h+var_C0], rdx
0x1400099a5  mov     dil, 1
0x1400099a8  movups  xmm0, xmmword ptr [rbp+57h+Src+1]
0x1400099ac  movups  xmmword ptr [rbp+57h+var_67], xmm0
0x1400099b0  movsd   qword ptr [rbp+57h+var_67+0Fh], xmm1
0x1400099b5  movups  xmm0, xmmword ptr [rbp+57h+var_67]
0x1400099b9  movups  xmmword ptr [rbp+57h+var_B7], xmm0
0x1400099bd  movsd   qword ptr [rbp+57h+var_B7+0Fh], xmm1
0x1400099c2  jmp     loc_1400098C0
0x1400099c7  mov     eax, dword ptr [rbp+57h+var_B7+0Fh]
0x1400099ca  mov     [rsp+110h+var_30], r15
0x1400099d2  mov     r15, qword ptr [rbp+57h+var_B7+7]
0x1400099d6  lea     ebx, ds:0[rax*8]
0x1400099dd  cmp     ebx, 46h ; 'F'
0x1400099e0  jbe     short loc_1400099EF
0x1400099e2  movzx   eax, byte ptr [r15+8]
0x1400099e7  shr     eax, 6
0x1400099ea  and     eax, 1
0x1400099ed  jmp     short loc_1400099F1
0x1400099ef  xor     eax, eax
0x1400099f1  mov     [r13+3B5h], al
0x1400099f8  lea     r14, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x1400099ff  lea     rsi, WPP_RECORDER_INITIALIZED
0x140009a06  test    al, al
0x140009a08  jz      short loc_140009A46
0x140009a0a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009a11  jz      short loc_140009A46
0x140009a13  mov     rcx, cs:WPP_GLOBAL_Control
0x140009a1a  cmp     byte ptr [rcx+29h], 5
0x140009a1e  jnb     short loc_140009A27
0x140009a20  cmp     word ptr [rcx+48h], 0
0x140009a25  jz      short loc_140009A46
0x140009a27  mov     rcx, [rcx+40h]
0x140009a2b  lea     rax, [r13+20h]
0x140009a2f  mov     [rsp+110h+var_E8], rax
0x140009a34  mov     r9d, 111h
0x140009a3a  mov     dl, 5
0x140009a3c  mov     [rsp+110h+var_F0], r14
0x140009a41  call    WPP_RECORDER_SF__MAC_
0x140009a46  test    dil, dil
0x140009a49  jnz     short loc_140009A4D
0x140009a4b  int     2Ch; Windows NT - assertion failure
0x140009a4d  cmp     ebx, 51h ; 'Q'
0x140009a50  jbe     short loc_140009A6B
0x140009a52  test    dil, dil
0x140009a55  jnz     short loc_140009A59
0x140009a57  int     2Ch; Windows NT - assertion failure
0x140009a59  test    byte ptr [r15+0Ah], 2
0x140009a5e  jz      short loc_140009A6B
0x140009a60  or      dword ptr [r13+378h], 80h
0x140009a6b  test    dil, dil
0x140009a6e  jnz     short loc_140009A72
0x140009a70  int     2Ch; Windows NT - assertion failure
0x140009a72  cmp     ebx, 52h ; 'R'
0x140009a75  jbe     short loc_140009A90
0x140009a77  test    dil, dil
0x140009a7a  jnz     short loc_140009A7E
0x140009a7c  int     2Ch; Windows NT - assertion failure
0x140009a7e  test    byte ptr [r15+0Ah], 4
0x140009a83  jz      short loc_140009A90
0x140009a85  or      dword ptr [r13+378h], 100h
0x140009a90  test    dil, dil
0x140009a93  jnz     short loc_140009A97
0x140009a95  int     2Ch; Windows NT - assertion failure
0x140009a97  cmp     ebx, 55h ; 'U'
0x140009a9a  jbe     short loc_140009AB0
0x140009a9c  test    dil, dil
0x140009a9f  jnz     short loc_140009AA3
0x140009aa1  int     2Ch; Windows NT - assertion failure
0x140009aa3  movzx   eax, byte ptr [r15+0Ah]
0x140009aa8  shr     eax, 5
0x140009aab  and     eax, 1
0x140009aae  jmp     short loc_140009AB2
0x140009ab0  xor     eax, eax
0x140009ab2  mov     [r13+3B6h], al
0x140009ab9  test    dil, dil
0x140009abc  jnz     short loc_140009AC0
0x140009abe  int     2Ch; Windows NT - assertion failure
0x140009ac0  cmp     ebx, 20h ; ' '
0x140009ac3  jbe     short loc_140009AD5
0x140009ac5  test    dil, dil
0x140009ac8  jnz     short loc_140009ACC
0x140009aca  int     2Ch; Windows NT - assertion failure
0x140009acc  movzx   eax, byte ptr [r15+4]
0x140009ad1  and     al, 1
0x140009ad3  jmp     short loc_140009AD7
0x140009ad5  xor     al, al
0x140009ad7  mov     [r13+3B7h], al
0x140009ade  test    dil, dil
0x140009ae1  jnz     short loc_140009AE5
0x140009ae3  int     2Ch; Windows NT - assertion failure
0x140009ae5  cmp     ebx, 36h ; '6'
0x140009ae8  jbe     short loc_140009B0D
0x140009aea  test    dil, dil
0x140009aed  jnz     short loc_140009AF1
0x140009aef  int     2Ch; Windows NT - assertion failure
0x140009af1  movzx   eax, byte ptr [r15+6]
0x140009af6  mov     r15, [rsp+110h+var_30]
0x140009afe  shr     eax, 6
0x140009b01  and     eax, 1
0x140009b04  mov     [r13+3B8h], al
0x140009b0b  jmp     short loc_140009B2E
0x140009b0d  mov     r15, [rsp+110h+var_30]
0x140009b15  xor     eax, eax
0x140009b17  mov     [r13+3B8h], al
0x140009b1e  jmp     short loc_140009B2E
0x140009b20  lea     rsi, WPP_RECORDER_INITIALIZED
0x140009b27  lea     r14, WPP_3599b95ca20c3e0ba686e8b05788690d_Traceguids
0x140009b2e  movups  xmm6, [rbp+57h+var_98]
0x140009b32  mov     r8d, 239A6F50h
0x140009b38  mov     byte ptr [rbp+57h+Src], 1
0x140009b3c  lea     rdx, [rbp+57h+Src]
0x140009b40  lea     rcx, [rbp+57h+var_B8]
0x140009b44  movups  xmmword ptr [rbp+57h+Src+8], xmm6
0x140009b48  call    wlan__parsers__details__FindTlv_wlan__parsers__TlvView_unsigned_char_unsigned_char___wlan__parsers__details__FindVendorSpecificInformationElement____2____lambda_1___
0x140009b4d  cmp     [rbp+57h+var_A0], 0
0x140009b51  mov     rdi, [rsp+110h+var_20]
0x140009b59  mov     rbx, [rsp+110h+arg_18]
0x140009b61  jz      short loc_140009B86
0x140009b63  mov     eax, dword ptr [rbp+57h+var_B7+0Fh]
0x140009b66  lea     eax, ds:0[rax*8]
0x140009b6d  test    eax, eax
0x140009b6f  jz      short loc_140009B7D
0x140009b71  mov     rax, qword ptr [rbp+57h+var_B7+7]
0x140009b75  movzx   ecx, byte ptr [rax]
0x140009b78  and     cl, 1
0x140009b7b  jmp     short loc_140009B7F
0x140009b7d  xor     cl, cl
0x140009b7f  mov     [r13+3B9h], cl
0x140009b86  mov     eax, [r13+378h]
0x140009b8d  test    al, 10h
0x140009b8f  jz      loc_140009C42
0x140009b95  mov     r8b, 0F4h
0x140009b98  lea     rdx, [rbp+57h+var_B8]
0x140009b9c  lea     rcx, [rbp+57h+var_98]
0x140009ba0  call    ?FindInformationElement@InformationElementBlobView@parsers@wlan@@QEBA?AV?$optional@V?$TlvView@EE@parsers@wlan@@@utl@@E@Z; wlan::parsers::InformationElementBlobView::FindInformationElement(uchar)
0x140009ba5  cmp     [rbp+57h+var_A0], 0
0x140009ba9  jz      short loc_140009BCB
0x140009bab  mov     eax, dword ptr [rbp+57h+var_B7+0Fh]
0x140009bae  lea     eax, ds:0[rax*8]
0x140009bb5  cmp     eax, 5
0x140009bb8  jbe     short loc_140009BCB
0x140009bba  mov     rax, qword ptr [rbp+57h+var_B7+7]
0x140009bbe  test    byte ptr [rax], 20h
0x140009bc1  jz      short loc_140009BCB
0x140009bc3  or      dword ptr [r13+378h], 20h
0x140009bcb  mov     r8b, 1
0x140009bce  lea     rdx, [rbp+57h+var_B8]
0x140009bd2  lea     rcx, [rbp+57h+var_98]
0x140009bd6  call    ?FindInformationElement@InformationElementBlobView@parsers@wlan@@QEBA?AV?$optional@V?$TlvView@EE@parsers@wlan@@@utl@@E@Z; wlan::parsers::InformationElementBlobView::FindInformationElement(uchar)
0x140009bdb  cmp     [rbp+57h+var_A0], 0
0x140009bdf  jz      short loc_140009C42
0x140009be1  mov     rdx, qword ptr [rbp+57h+var_B7+7]
0x140009be5  xor     eax, eax
0x140009be7  mov     ecx, eax
0x140009be9  cmp     rcx, qword ptr [rbp+57h+var_B7+0Fh]
0x140009bed  jnb     short loc_140009C01
0x140009bef  cmp     byte ptr [rax+rdx], 0FBh
0x140009bf3  jz      short loc_140009BF9
0x140009bf5  inc     eax
0x140009bf7  jmp     short loc_140009BE7
0x140009bf9  or      dword ptr [r13+378h], 40h
0x140009c01  mov     eax, [r13+378h]
0x140009c08  test    al, 40h
0x140009c0a  jnz     short loc_140009C42
0x140009c0c  mov     r8b, 32h ; '2'
0x140009c0f  lea     rdx, [rbp+57h+var_B8]
0x140009c13  lea     rcx, [rbp+57h+var_98]
0x140009c17  call    ?FindInformationElement@InformationElementBlobView@parsers@wlan@@QEBA?AV?$optional@V?$TlvView@EE@parsers@wlan@@@utl@@E@Z; wlan::parsers::InformationElementBlobView::FindInformationElement(uchar)
0x140009c1c  cmp     [rbp+57h+var_A0], 0
0x140009c20  jz      short loc_140009C42
0x140009c22  mov     rdx, qword ptr [rbp+57h+var_B7+7]
0x140009c26  xor     eax, eax
0x140009c28  mov     ecx, eax
0x140009c2a  cmp     rcx, qword ptr [rbp+57h+var_B7+0Fh]
0x140009c2e  jnb     short loc_140009C42
0x140009c30  cmp     byte ptr [rax+rdx], 0FBh
0x140009c34  jz      short loc_140009C3A
0x140009c36  inc     eax
0x140009c38  jmp     short loc_140009C28
0x140009c3a  or      dword ptr [r13+378h], 40h
0x140009c42  mov     r8b, 6Bh ; 'k'
0x140009c45  mov     byte ptr [r13+2Ch], 0
0x140009c4a  lea     rdx, [rbp+57h+Src]
0x140009c4e  mov     byte ptr [rbp+57h+Src], 1
0x140009c52  lea     rcx, [rbp+57h+var_B8]
0x140009c56  movups  xmmword ptr [rbp+57h+Src+8], xmm6
0x140009c5a  call    wlan__parsers__details__FindTlv_wlan__parsers__TlvView_unsigned_char_unsigned_char___wlan__parsers__details__FindExtendedInformationElement____2____lambda_1___
0x140009c5f  cmp     [rbp+57h+var_A0], 0
0x140009c63  movaps  xmm6, [rsp+110h+var_48+8]
0x140009c6b  jz      loc_140009D10
0x140009c71  mov     rax, qword ptr [rbp+57h+var_B7+0Fh]
0x140009c75  cmp     rax, 0Bh
0x140009c79  jb      short loc_140009CDE
0x140009c7b  mov     rdx, qword ptr [rbp+57h+var_B7+7]
0x140009c7f  add     rdx, 4
0x140009c83  mov     byte ptr [r13+2Ch], 1
0x140009c88  mov     eax, [rdx]
0x140009c8a  mov     [r13+26h], eax
0x140009c8e  movzx   eax, word ptr [rdx+4]
0x140009c92  or      dword ptr [r13+378h], 400h
0x140009c9d  mov     [r13+2Ah], ax
0x140009ca2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009ca9  jz      short loc_140009D10
0x140009cab  mov     rcx, cs:WPP_GLOBAL_Control
0x140009cb2  cmp     byte ptr [rcx+29h], 5
0x140009cb6  jnb     short loc_140009CBF
0x140009cb8  cmp     word ptr [rcx+48h], 0
  ... truncated ...
```
