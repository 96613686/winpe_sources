# ShareClass::IM_DecodeFastPathInput(uchar *,int,uint,uint)

- ea: `0x18018520c`
- end: `0x180185d6b`
- name: `?IM_DecodeFastPathInput@ShareClass@@QEAAXPEAEHII@Z`
- size: `2911`
- prototype: `void __fastcall(ShareClass *this, unsigned __int8 *, int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x180038394`
- `0x18007015c`

## callees

- `0x18000116c`
- `0x180001f84`
- `0x180002170`
- `0x180002840`
- `0x180005a80`
- `0x180008628`
- `0x18000bb2c`
- `0x18000bbec`
- `0x18004b554`
- `0x180072b40`
- `0x180072cdc`
- `0x18007e9e0`
- `0x18017adb0`
- `0x1801847e8`
- `0x180184e28`
- `0x18018520c`

## string_xrefs

- `0x18018531b`: `IM_DecodeFastPathInput`
- `0x180185876`: `IM_DecodeFastPathInput`
- `0x180185912`: `IM_DecodeFastPathInput`
- `0x18018599d`: `IM_DecodeFastPathInput`
- `0x180185a1d`: `IM_DecodeFastPathInput`
- `0x180185a8c`: `IM_DecodeFastPathInput`
- `0x180185afb`: `IM_DecodeFastPathInput`
- `0x180185bad`: `IM_DecodeFastPathInput`
- `0x180185c3f`: `IM_DecodeFastPathInput`
- `0x180185c7d`: `IM_DecodeFastPathInput`
- `0x180185cb7`: `IM_DecodeFastPathInput`
- `0x180185a43`: `Ran out of space reading keyboard events`
- `0x180185ab2`: `Ran out of space reading keyboard events`
- `0x180185c65`: `Ran out of space reading keyboard events`
- `0x180185ca3`: `Ran out of space reading keyboard events`
- `0x180185cdd`: `Out of data reading input events`

## pseudocode

```c
void __fastcall ShareClass::IM_DecodeFastPathInput(
        ShareClass *this,
        unsigned __int8 *a2,
        int a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int v5; // r13d
  unsigned int v6; // ebx
  unsigned __int8 *v7; // rdi
  ShareClass *v8; // r10
  int v9; // r8d
  unsigned int v10; // r14d
  int v11; // r9d
  int v12; // ecx
  int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // r15d
  __int64 v16; // r12
  int v17; // esi
  const char *v18; // rcx
  int v19; // eax
  __int16 *v20; // rdx
  int v21; // r15d
  unsigned int v22; // esi
  unsigned int v23; // r12d
  int v24; // eax
  int v25; // eax
  int v26; // r8d
  int v27; // r9d
  unsigned int v28; // r15d
  __int64 v29; // rsi
  int v30; // r12d
  int v31; // ecx
  int v32; // eax
  int v33; // eax
  char *v34; // rdx
  const char **v35; // rax
  __int16 *v36; // rdx
  const char **v37; // rax
  const char *v38; // rax
  const char **v39; // [rsp+30h] [rbp-D0h]
  const char **v40; // [rsp+30h] [rbp-D0h]
  const char **v41; // [rsp+40h] [rbp-C0h]
  const char **v42; // [rsp+40h] [rbp-C0h]
  const char *v43; // [rsp+70h] [rbp-90h] BYREF
  const char *v44; // [rsp+78h] [rbp-88h] BYREF
  int v45; // [rsp+80h] [rbp-80h] BYREF
  const char *v46; // [rsp+88h] [rbp-78h] BYREF
  const char *v47; // [rsp+90h] [rbp-70h] BYREF
  const char *v48; // [rsp+98h] [rbp-68h] BYREF
  const char *v49; // [rsp+A0h] [rbp-60h] BYREF
  ShareClass *v50; // [rsp+A8h] [rbp-58h]
  const char *v51; // [rsp+B0h] [rbp-50h] BYREF
  const char *v52; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v53[240]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = a5;
  v6 = a4;
  LODWORD(v49) = a3;
  v7 = a2;
  v50 = this;
  v8 = this;
  if ( !a5 )
  {
    if ( !a4 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v49) = 0;
        v43 = "IM_DecodeFastPathInput";
        LODWORD(v48) = 359;
        v47 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\aimapi.cpp";
        v46 = "Len %u too short for DataLength";
        v45 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)this,
          (unsigned int)&word_1802AA02E,
          a3,
          a4,
          (__int64)&v46,
          (__int64)&v45,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&v43,
          (__int64)&v49);
      }
      goto LABEL_101;
    }
    v5 = *a2;
    v7 = a2 + 1;
    v6 = a4 - 1;
  }
  v9 = 0;
  v10 = 0;
  LODWORD(v48) = 0;
  if ( !v5 )
    return;
  while ( 1 )
  {
    v11 = 10;
    if ( !v6 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_101;
      LODWORD(v43) = 630;
      v52 = "IM_DecodeFastPathInput";
      v34 = &byte_1802A9B17;
      v44 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\aimapi.cpp";
      v38 = "Out of data reading input events";
      goto LABEL_99;
    }
    LODWORD(this) = *v7 & 0xE0;
    if ( (*v7 & 0xE0) == 0 )
    {
      v28 = 10;
      if ( v5 - v10 < 0xA )
        v28 = v5 - v10;
      if ( (unsigned int)dword_1802BB170 > 5 )
      {
        LODWORD(v43) = v9;
        LODWORD(v47) = v28;
        LODWORD(v46) = v5;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1802BB170,
          (unsigned int)&word_1802AA136,
          v9,
          10,
          (__int64)&v46,
          (__int64)&v47,
          (__int64)&v43);
        v8 = v50;
      }
      v29 = 0;
      v30 = 0;
      if ( !v28 )
      {
LABEL_71:
        v10 = v30 + v10 - 1;
        if ( !(_DWORD)v49 )
        {
          v32 = WDICART_IcaChannelInput(*(_QWORD *)(*(_QWORD *)v50 + 8LL), 0, 0, v11, (__int64)v53, 12 * (int)v29);
          LODWORD(this) = (_DWORD)CallbackContext;
          if ( (unsigned int)CallbackContext > 5 )
          {
            LODWORD(v43) = v32;
            v44 = "Return from keyboard input injection %lu";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (_DWORD)CallbackContext,
              (unsigned int)byte_1802AA005,
              v9,
              v11,
              (__int64)&v44,
              (__int64)&v43);
          }
        }
        if ( (unsigned int)dword_1802BB170 > 5 )
        {
          v20 = (__int16 *)&unk_1802A9FD8;
LABEL_41:
          LODWORD(v43) = (_DWORD)v48;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (_DWORD)this,
            (_DWORD)v20,
            v9,
            v11,
            (__int64)&v43);
        }
LABEL_42:
        v9 = (_DWORD)v48 + 1;
        LODWORD(v48) = (_DWORD)v48 + 1;
        goto LABEL_16;
      }
      while ( v6 )
      {
        if ( (*v7 & 0xE0) != 0 )
          goto LABEL_71;
        if ( v6 < 2 )
        {
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_101;
          LODWORD(v43) = 402;
          v52 = "IM_DecodeFastPathInput";
          v34 = byte_1802A9F93;
          v44 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\aimapi.cpp";
          v38 = "Ran out of space reading keyboard events";
          goto LABEL_99;
        }
        v44 = (const char *)(3 * v29);
        if ( (unsigned int)ShareClass::IMConvertFastPathKeyboardToEvent(
                             v8,
                             v7,
                             (struct _KEYBOARD_INPUT_DATA *)&v53[12 * v29]) )
        {
          if ( (unsigned int)CallbackContext > 5 )
          {
            v31 = (int)v44;
            LODWORD(v43) = v29;
            LOWORD(v45) = *(_WORD *)&v53[4 * (_QWORD)v44 + 4];
            LOWORD(v51) = *(_WORD *)&v53[4 * (_QWORD)v44 + 2];
            v44 = "Add kbd evt to batch index %d: MakeCode(%x) flags(%#x)";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
              v31,
              (unsigned int)&unk_1802AA0D0,
              v9,
              v11,
              (__int64)&v44,
              (__int64)&v43,
              (__int64)&v51,
              (__int64)&v45);
          }
          v29 = (unsigned int)(v29 + 1);
        }
        v8 = v50;
        v7 += 2;
        v6 -= 2;
        if ( ++v30 >= v28 )
          goto LABEL_71;
      }
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_101;
      LODWORD(v43) = 411;
      v52 = "IM_DecodeFastPathInput";
      v34 = (char *)&word_1802A9F4E;
      v44 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\aimapi.cpp";
      v38 = "Ran out of space reading keyboard events";
LABEL_99:
      v46 = v38;
      v41 = &v52;
      v39 = &v44;
      v35 = &v46;
      goto LABEL_100;
    }
    v12 = (_DWORD)this - 32;
    if ( !v12 )
      goto LABEL_23;
    v12 -= 32;
    if ( !v12 )
      goto LABEL_23;
    v13 = v12 - 32;
    if ( !v13 )
    {
      ShareClass::IMDoSync(v8, *v7++ & 0x1F);
      --v6;
LABEL_15:
      v9 = (int)v48;
      goto LABEL_16;
    }
    LODWORD(this) = v13 - 32;
    if ( (_DWORD)this )
    {
      v12 = (_DWORD)this - 32;
      if ( v12 )
      {
        if ( v12 == 32 )
        {
          ++v7;
          if ( --v6 < 4 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(v43) = v6;
              v44 = "IM_DecodeFastPathInput";
              LODWORD(v47) = 613;
              v49 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\aimapi.cpp";
              v48 = "Out of data decoding QoE Input TS PDU bytes:(%d)";
              LODWORD(v46) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                (_DWORD)v7,
                (unsigned int)word_1802A9C4A,
                v9,
                10,
                (__int64)&v48,
                (__int64)&v46,
                (__int64)&v49,
                (__int64)&v47,
                (__int64)&v44,
                (__int64)&v43);
            }
            goto LABEL_101;
          }
          v14 = *(_DWORD *)v7;
          v7 += 4;
          v6 -= 4;
          Log_QOE_ETW_Event(v14);
          goto LABEL_15;
        }
        if ( (unsigned int)CallbackContext <= 2 )
        {
LABEL_81:
          WDW_LogAndDisconnect(*(_QWORD *)v8, 1, 207, (_DWORD)v7, 1);
          return;
        }
        v33 = *v7 & 0xE0;
        LODWORD(v47) = 623;
        LODWORD(v43) = v33;
        v44 = "IM_DecodeFastPathInput";
        v49 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\aimapi.cpp";
        v48 = "Unrecognized imPacket (%d)";
        LODWORD(v46) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v12,
          (unsigned int)&word_1802A9BF6,
          v9,
          10,
          (__int64)&v48,
          (__int64)&v46,
          (__int64)&v49,
          (__int64)&v47,
          (__int64)&v44,
          (__int64)&v43);
LABEL_80:
        v8 = v50;
        goto LABEL_81;
      }
      if ( !*(_DWORD *)(*(_QWORD *)v8 + 1360LL) && !*(_DWORD *)(*(_QWORD *)v8 + 1368LL) )
      {
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_81;
        LODWORD(v43) = 488;
        v44 = "IM_DecodeFastPathInput";
        LODWORD(v47) = -2147467259;
        v46 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\aimapi.cpp";
        v49 = "Received a relative mouse mode PDU when the stack does not support it.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          0,
          (unsigned int)qword_1802A9EE0,
          v9,
          10,
          (__int64)&v49,
          (__int64)&v47,
          (__int64)&v46,
          (__int64)&v43,
          (__int64)&v44);
        goto LABEL_80;
      }
LABEL_23:
      v15 = 10;
      if ( v5 - v10 < 0xA )
        v15 = v5 - v10;
      v16 = 0;
      if ( (unsigned int)dword_1802BB170 > 5 )
      {
        v45 = v9;
        LODWORD(v51) = v15;
        LODWORD(v46) = v5;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1802BB170,
          (unsigned int)&dword_1802A9D4C,
          v9,
          10,
          (__int64)&v46,
          (__int64)&v51,
          (__int64)&v45);
        v8 = v50;
      }
      v17 = 0;
      if ( v15 )
      {
        while ( v6 )
        {
          LOBYTE(v12) = *v7 & 0xE0;
          if ( (((_BYTE)v12 - 32) & 0x5F) != 0 || (_BYTE)v12 == 0xC0 )
            goto LABEL_37;
          if ( v6 < 7 )
          {
            if ( (unsigned int)CallbackContext <= 2 )
              goto LABEL_101;
            LODWORD(v48) = 554;
            v44 = "IM_DecodeFastPathInput";
            v36 = (__int16 *)&dword_1802A9DF4;
            v51 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\aimapi.cpp";
            v52 = "Out of data decoding mouse, i=%u, j=%u, NumEvents=%u, DataLen=%u";
            v42 = &v44;
            v40 = &v51;
            v37 = &v52;
            goto LABEL_90;
          }
          v43 = (const char *)(3 * v16);
          if ( (unsigned int)ShareClass::IMConvertMousePacketToEvent(
                               v8,
                               (struct tagTS_POINTER_EVENT *)(v7 + 1),
                               (struct _MOUSE_INPUT_DATA *)&v53[24 * v16],
                               (_BYTE)v12 == 64,
                               (_BYTE)v12 == 0xA0) )
          {
            if ( (unsigned int)CallbackContext > 5 )
            {
              v18 = v43;
              LODWORD(v43) = v16;
              LOWORD(v51) = *(_WORD *)&v53[8 * (_QWORD)v18 + 4];
              LOWORD(v45) = *(_WORD *)&v53[8 * (_QWORD)v18 + 2];
              LODWORD(v46) = *(_DWORD *)&v53[8 * (_QWORD)v18 + 16];
              LODWORD(v47) = *(_DWORD *)&v53[8 * (_QWORD)v18 + 12];
              v44 = "Add mouse evt to batch index %u: x(%ld) y(%ld) flags(%#hx) buttonflags(%#hx)";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
                (_DWORD)v18,
                (unsigned int)byte_1802A9C9B,
                v9,
                v11,
                (__int64)&v44,
                (__int64)&v43,
                (__int64)&v47,
                (__int64)&v46,
                (__int64)&v45,
                (__int64)&v51);
            }
            v16 = (unsigned int)(v16 + 1);
          }
          v8 = v50;
          v7 += 7;
          v6 -= 7;
          if ( ++v17 >= v15 )
            goto LABEL_37;
        }
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v48) = 567;
          v52 = "IM_DecodeFastPathInput";
          v36 = word_1802A9D92;
          v44 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\aimapi.cpp";
          v51 = "Out of data decoding mouse, i=%u, j=%u, NumEvents=%u, DataLen=%u";
          v42 = &v52;
          v40 = &v44;
          v37 = &v51;
LABEL_90:
          LODWORD(v43) = v6;
          v45 = -2147467259;
          LODWORD(v49) = v10;
          LODWORD(v46) = v17;
          LODWORD(v47) = v5;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v12,
            (_DWORD)v36,
            v9,
            v11,
            (__int64)v37,
            (__int64)&v45,
            (__int64)v40,
            (__int64)&v48,
            (__int64)v42,
            (__int64)&v49,
            (__int64)&v46,
            (__int64)&v47,
            (__int64)&v43);
          goto LABEL_101;
        }
        goto LABEL_101;
      }
LABEL_37:
      v10 = v17 + v10 - 1;
      v19 = WDICART_IcaChannelInput(*(_QWORD *)(*(_QWORD *)v50 + 8LL), 1, 0, v11, (__int64)v53, 24 * (int)v16);
      LODWORD(this) = (_DWORD)CallbackContext;
      if ( (unsigned int)CallbackContext > 5 )
      {
        LODWORD(v43) = v19;
        v44 = "Return from mouse input injection %lu";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_1802A9BCD,
          v9,
          v11,
          (__int64)&v44,
          (__int64)&v43);
      }
      if ( (unsigned int)dword_1802BB170 > 5 )
      {
        v20 = &word_1802A9B9E;
        goto LABEL_41;
      }
      goto LABEL_42;
    }
    v21 = 0;
    v22 = v5 - v10;
    v23 = 0;
    if ( v5 - v10 >= 0xA )
    {
      v22 = 10;
      break;
    }
    if ( v22 )
      break;
LABEL_54:
    v10 = v23 + v10 - 1;
    if ( !(_DWORD)v49 )
    {
      v25 = WDICART_IcaChannelInput(*(_QWORD *)(*(_QWORD *)v8 + 8LL), 0, 0, v11, (__int64)v53, 12 * v21);
      LODWORD(this) = (_DWORD)CallbackContext;
      if ( (unsigned int)CallbackContext > 5 )
      {
        v45 = v25;
        v43 = "Return from keyboard input injection %lu";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_1802A9F25,
          v26,
          v27,
          (__int64)&v43,
          (__int64)&v45);
      }
      goto LABEL_15;
    }
LABEL_16:
    if ( ++v10 >= v5 )
      return;
    v8 = v50;
  }
  while ( v6 )
  {
    if ( (*v7 & 0xE0) != 0x80 )
      goto LABEL_53;
    if ( v6 < 3 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_101;
      LODWORD(v43) = 455;
      v44 = "IM_DecodeFastPathInput";
      v34 = byte_1802A9E9B;
      v46 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\aimapi.cpp";
      v49 = "Ran out of space reading keyboard events";
      v41 = &v44;
      v39 = &v46;
      v35 = &v49;
      goto LABEL_100;
    }
    v24 = ShareClass::IMConvertFastPathKeyboardToEvent(v8, v7, (struct _KEYBOARD_INPUT_DATA *)&v53[12 * v21]);
    v8 = v50;
    LODWORD(this) = v21 + 1;
    if ( !v24 )
      LODWORD(this) = v21;
    v7 += 3;
    v6 -= 3;
    ++v23;
    v21 = (int)this;
    if ( v23 >= v22 )
    {
LABEL_53:
      v9 = (int)v48;
      goto LABEL_54;
    }
  }
  if ( (unsigned int)CallbackContext <= 2 )
    goto LABEL_101;
  LODWORD(v43) = 464;
  v44 = "IM_DecodeFastPathInput";
  v34 = (char *)&word_1802A9E56;
  v46 = "onecore\\termsrv\\rdpplatform\\drivers\\rdp\\rdpwd\\aimapi.cpp";
  v49 = "Ran out of space reading keyboard events";
  v41 = &v44;
  v39 = &v46;
  v35 = &v49;
LABEL_100:
  LODWORD(v47) = -2147467259;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
    (_DWORD)this,
    (_DWORD)v34,
    v9,
    v11,
    (__int64)v35,
    (__int64)&v47,
    (__int64)v39,
    (__int64)&v43,
    (__int64)v41);
LABEL_101:
  WDW_LogAndDisconnect(*(_QWORD *)v50, 1, 222, (_DWORD)v7, v6);
}

```

## disassembly

```asm
0x18018520c  mov     [rsp-8+arg_10], rbx
0x180185211  push    rbp
0x180185212  push    rsi
0x180185213  push    rdi
0x180185214  push    r12
0x180185216  push    r13
0x180185218  push    r14
0x18018521a  push    r15
0x18018521c  lea     rbp, [rsp-0C0h]
0x180185224  sub     rsp, 1C0h
0x18018522b  mov     rax, cs:__security_cookie
0x180185232  xor     rax, rsp
0x180185235  mov     [rbp+0F0h+var_40], rax
0x18018523c  mov     r13d, [rbp+0F0h+arg_20]
0x180185243  mov     ebx, r9d
0x180185246  mov     dword ptr [rbp+0F0h+var_150], r8d
0x18018524a  mov     rdi, rdx
0x18018524d  mov     [rbp+0F0h+var_148], rcx
0x180185251  mov     r10, rcx
0x180185254  test    r13d, r13d
0x180185257  jnz     short loc_18018526B
0x180185259  cmp     ebx, 1
0x18018525c  jb      loc_18018530C
0x180185262  movzx   r13d, byte ptr [rdx]
0x180185266  inc     rdi
0x180185269  dec     ebx
0x18018526b  xor     r8d, r8d
0x18018526e  xor     r14d, r14d
0x180185271  mov     dword ptr [rbp+0F0h+var_158], r8d
0x180185275  test    r13d, r13d
0x180185278  jz      loc_180185D41
0x18018527e  mov     r9d, 0Ah
0x180185284  cmp     ebx, 1
0x180185287  jb      loc_180185CAC
0x18018528d  movzx   edx, byte ptr [rdi]
0x180185290  mov     ecx, edx
0x180185292  and     ecx, 0E0h
0x180185298  jz      loc_1801856BC
0x18018529e  sub     ecx, 20h ; ' '
0x1801852a1  jz      loc_1801853AF
0x1801852a7  sub     ecx, 20h ; ' '
0x1801852aa  jz      loc_1801853AF
0x1801852b0  sub     ecx, 20h ; ' '
0x1801852b3  jz      loc_1801856A7
0x1801852b9  sub     ecx, 20h ; ' '
0x1801852bc  jz      loc_1801855BE
0x1801852c2  sub     ecx, 20h ; ' '
0x1801852c5  jz      loc_180185396
0x1801852cb  cmp     ecx, 20h ; ' '
0x1801852ce  jnz     loc_1801858E9
0x1801852d4  inc     rdi
0x1801852d7  dec     ebx
0x1801852d9  mov     rcx, rdi
0x1801852dc  cmp     ebx, 4
0x1801852df  jb      loc_180185867
0x1801852e5  mov     ecx, [rcx]; unsigned int
0x1801852e7  add     rdi, 4
0x1801852eb  add     ebx, 0FFFFFFFCh
0x1801852ee  call    ?Log_QOE_ETW_Event@@YAXI@Z; Log_QOE_ETW_Event(uint)
0x1801852f3  mov     r8d, dword ptr [rbp+0F0h+var_158]
0x1801852f7  inc     r14d
0x1801852fa  cmp     r14d, r13d
0x1801852fd  jnb     loc_180185D41
0x180185303  mov     r10, [rbp+0F0h+var_148]
0x180185307  jmp     loc_18018527E
0x18018530c  mov     eax, cs:CallbackContext
0x180185312  cmp     eax, 2
0x180185315  jbe     loc_180185D23
0x18018531b  lea     rax, aImDecodefastpa; "IM_DecodeFastPathInput"
0x180185322  mov     dword ptr [rbp+0F0h+var_150], ebx
0x180185325  mov     [rsp+1F0h+var_180], rax
0x18018532a  lea     rdx, word_1802AA02E
0x180185331  lea     rax, aOnecoreTermsrv_43; "onecore\\termsrv\\rdpplatform\\drivers"...
0x180185338  mov     dword ptr [rbp+0F0h+var_158], 167h
0x18018533f  mov     [rbp+0F0h+var_160], rax
0x180185343  lea     rax, aLenUTooShortFo; "Len %u too short for DataLength"
0x18018534a  mov     [rbp+0F0h+var_168], rax
0x18018534e  lea     rax, [rbp+0F0h+var_150]
0x180185352  mov     [rsp+1F0h+var_1A8], rax
0x180185357  lea     rax, [rsp+1F0h+var_180]
0x18018535c  mov     [rsp+1F0h+var_1B0], rax
0x180185361  lea     rax, [rbp+0F0h+var_158]
0x180185365  mov     [rsp+1F0h+var_1B8], rax
0x18018536a  lea     rax, [rbp+0F0h+var_160]
0x18018536e  mov     [rsp+1F0h+var_1C0], rax
0x180185373  lea     rax, [rbp+0F0h+var_170]
0x180185377  mov     [rsp+1F0h+var_1C8], rax
0x18018537c  lea     rax, [rbp+0F0h+var_168]
0x180185380  mov     [rbp+0F0h+var_170], 80004005h
0x180185387  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x18018538c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180185391  jmp     loc_180185D23
0x180185396  mov     rax, [r10]
0x180185399  cmp     dword ptr [rax+550h], 0
0x1801853a0  jnz     short loc_1801853AF
0x1801853a2  cmp     dword ptr [rax+558h], 0
0x1801853a9  jz      loc_180185992
0x1801853af  mov     eax, r13d
0x1801853b2  mov     r15d, r9d
0x1801853b5  sub     eax, r14d
0x1801853b8  cmp     eax, r9d
0x1801853bb  cmovb   r15d, eax
0x1801853bf  mov     eax, cs:dword_1802BB170
0x1801853c5  xor     r12d, r12d
0x1801853c8  cmp     eax, 5
0x1801853cb  jbe     short loc_18018540B
0x1801853cd  lea     rax, [rbp+0F0h+var_170]
0x1801853d1  mov     [rbp+0F0h+var_170], r8d
0x1801853d5  mov     [rsp+1F0h+var_1C0], rax
0x1801853da  lea     rdx, dword_1802A9D4C
0x1801853e1  lea     rax, [rbp+0F0h+var_140]
0x1801853e5  mov     dword ptr [rbp+0F0h+var_140], r15d
0x1801853e9  mov     [rsp+1F0h+var_1C8], rax
0x1801853ee  lea     rcx, dword_1802BB170
0x1801853f5  lea     rax, [rbp+0F0h+var_168]
0x1801853f9  mov     dword ptr [rbp+0F0h+var_168], r13d
0x1801853fd  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x180185402  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180185407  mov     r10, [rbp+0F0h+var_148]
0x18018540b  xor     esi, esi
0x18018540d  test    r15d, r15d
0x180185410  jz      loc_18018551A
0x180185416  cmp     ebx, 1
0x180185419  jb      loc_180185B9E
0x18018541f  mov     cl, [rdi]
0x180185421  and     cl, 0E0h
0x180185424  lea     eax, [rcx-20h]
0x180185427  test    al, 5Fh
0x180185429  jnz     loc_18018551A
0x18018542f  cmp     cl, 0C0h
0x180185432  jz      loc_18018551A
0x180185438  cmp     ebx, 7
0x18018543b  jb      loc_180185AEC
0x180185441  xor     eax, eax
0x180185443  lea     rdx, [r12+r12*2]
0x180185447  cmp     cl, 0A0h
0x18018544a  mov     [rsp+1F0h+var_180], rdx
0x18018544f  lea     r8, [rbp+0F0h+var_130]
0x180185453  setz    al
0x180185456  lea     r8, [r8+rdx*8]; struct _MOUSE_INPUT_DATA *
0x18018545a  xor     r9d, r9d
0x18018545d  mov     [rsp+1F0h+var_1D0], eax; int
0x180185461  cmp     cl, 40h ; '@'
0x180185464  lea     rdx, [rdi+1]; struct tagTS_POINTER_EVENT *
0x180185468  mov     rcx, r10; this
0x18018546b  setz    r9b; int
0x18018546f  call    ?IMConvertMousePacketToEvent@ShareClass@@QEAAHPEFAUtagTS_POINTER_EVENT@@PEAU_MOUSE_INPUT_DATA@@HH@Z; ShareClass::IMConvertMousePacketToEvent(tagTS_POINTER_EVENT *,_MOUSE_INPUT_DATA *,int,int)
0x180185474  test    eax, eax
0x180185476  jz      loc_180185504
0x18018547c  mov     eax, cs:CallbackContext
0x180185482  cmp     eax, 5
0x180185485  jbe     short loc_180185501
0x180185487  mov     rcx, [rsp+1F0h+var_180]
0x18018548c  lea     rdx, byte_1802A9C9B
0x180185493  mov     dword ptr [rsp+1F0h+var_180], r12d
0x180185498  movzx   eax, [rbp+rcx*8+0F0h+var_12C]
0x18018549d  mov     word ptr [rbp+0F0h+var_140], ax
0x1801854a1  movzx   eax, [rbp+rcx*8+0F0h+var_12E]
0x1801854a6  mov     word ptr [rbp+0F0h+var_170], ax
0x1801854aa  mov     eax, [rbp+rcx*8+0F0h+var_120]
0x1801854ae  mov     dword ptr [rbp+0F0h+var_168], eax
0x1801854b1  mov     eax, [rbp+rcx*8+0F0h+var_124]
0x1801854b5  mov     dword ptr [rbp+0F0h+var_160], eax
0x1801854b8  lea     rax, aAddMouseEvtToB; "Add mouse evt to batch index %u: x(%ld)"...
0x1801854bf  mov     [rsp+1F0h+var_178], rax
0x1801854c4  lea     rax, [rbp+0F0h+var_140]
0x1801854c8  mov     [rsp+1F0h+var_1A8], rax
0x1801854cd  lea     rax, [rbp+0F0h+var_170]
0x1801854d1  mov     [rsp+1F0h+var_1B0], rax
0x1801854d6  lea     rax, [rbp+0F0h+var_168]
0x1801854da  mov     [rsp+1F0h+var_1B8], rax
0x1801854df  lea     rax, [rbp+0F0h+var_160]
0x1801854e3  mov     [rsp+1F0h+var_1C0], rax
0x1801854e8  lea     rax, [rsp+1F0h+var_180]
0x1801854ed  mov     [rsp+1F0h+var_1C8], rax
0x1801854f2  lea     rax, [rsp+1F0h+var_178]
0x1801854f7  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x1801854fc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapperByVal@$01@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapperByVal@$01@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &)
0x180185501  inc     r12d
0x180185504  mov     r10, [rbp+0F0h+var_148]
0x180185508  add     rdi, 7
0x18018550c  add     ebx, 0FFFFFFF9h
0x18018550f  inc     esi
0x180185511  cmp     esi, r15d
0x180185514  jb      loc_180185416
0x18018551a  mov     rcx, [rbp+0F0h+var_148]
0x18018551e  lea     eax, [r12+r12*2]
0x180185522  shl     eax, 3
0x180185525  xor     r8d, r8d
0x180185528  mov     dword ptr [rsp+1F0h+var_1C8], eax
0x18018552c  dec     r14d
0x18018552f  lea     rax, [rbp+0F0h+var_130]
0x180185533  add     r14d, esi
0x180185536  mov     rcx, [rcx]
0x180185539  lea     edx, [r8+1]
0x18018553d  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x180185542  mov     rcx, [rcx+8]
0x180185546  call    WDICART_IcaChannelInput
0x18018554b  mov     ecx, cs:CallbackContext
0x180185551  cmp     ecx, 5
0x180185554  jbe     short loc_180185586
0x180185556  mov     dword ptr [rsp+1F0h+var_180], eax
0x18018555a  lea     rdx, byte_1802A9BCD
0x180185561  lea     rax, aReturnFromMous; "Return from mouse input injection %lu"
0x180185568  mov     [rsp+1F0h+var_178], rax
0x18018556d  lea     rax, [rsp+1F0h+var_180]
0x180185572  mov     [rsp+1F0h+var_1C8], rax
0x180185577  lea     rax, [rsp+1F0h+var_178]
0x18018557c  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x180185581  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180185586  mov     eax, cs:dword_1802BB170
0x18018558c  cmp     eax, 5
0x18018558f  jbe     short loc_1801855AE
0x180185591  lea     rdx, word_1802A9B9E
0x180185598  mov     eax, dword ptr [rbp+0F0h+var_158]
0x18018559b  mov     dword ptr [rsp+1F0h+var_180], eax
0x18018559f  lea     rax, [rsp+1F0h+var_180]
0x1801855a4  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x1801855a9  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1801855ae  mov     r8d, dword ptr [rbp+0F0h+var_158]
0x1801855b2  inc     r8d
0x1801855b5  mov     dword ptr [rbp+0F0h+var_158], r8d
0x1801855b9  jmp     loc_1801852F7
0x1801855be  mov     esi, r13d
0x1801855c1  xor     r15d, r15d
0x1801855c4  sub     esi, r14d
0x1801855c7  xor     r12d, r12d
0x1801855ca  cmp     esi, r9d
0x1801855cd  jnb     short loc_1801855D5
0x1801855cf  test    esi, esi
0x1801855d1  jz      short loc_180185630
0x1801855d3  jmp     short loc_1801855D8
0x1801855d5  mov     esi, r9d
0x1801855d8  cmp     ebx, 1
0x1801855db  jb      loc_180185A7D
0x1801855e1  mov     al, [rdi]
0x1801855e3  and     al, 0E0h
0x1801855e5  cmp     al, 80h
0x1801855e7  jnz     short loc_18018562C
0x1801855e9  cmp     ebx, 3
0x1801855ec  jb      loc_180185A0E
0x1801855f2  mov     eax, r15d
0x1801855f5  lea     r8, [rbp+0F0h+var_130]
0x1801855f9  mov     rdx, rdi; unsigned __int8 *
0x1801855fc  lea     rcx, [rax+rax*2]
0x180185600  lea     r8, [r8+rcx*4]; struct _KEYBOARD_INPUT_DATA *
0x180185604  mov     rcx, r10; this
0x180185607  call    ?IMConvertFastPathKeyboardToEvent@ShareClass@@QEAAHPEAEPEAU_KEYBOARD_INPUT_DATA@@@Z; ShareClass::IMConvertFastPathKeyboardToEvent(uchar *,_KEYBOARD_INPUT_DATA *)
0x18018560c  mov     r10, [rbp+0F0h+var_148]
0x180185610  lea     ecx, [r15+1]
0x180185614  test    eax, eax
0x180185616  cmovz   ecx, r15d
0x18018561a  add     rdi, 3
0x18018561e  add     ebx, 0FFFFFFFDh
0x180185621  inc     r12d
0x180185624  mov     r15d, ecx
0x180185627  cmp     r12d, esi
0x18018562a  jb      short loc_1801855D8
0x18018562c  mov     r8d, dword ptr [rbp+0F0h+var_158]
0x180185630  dec     r14d
0x180185633  add     r14d, r12d
0x180185636  cmp     dword ptr [rbp+0F0h+var_150], 0
0x18018563a  jnz     loc_1801852F7
0x180185640  mov     rcx, [r10]
0x180185643  lea     eax, [r15+r15*2]
0x180185647  shl     eax, 2
0x18018564a  xor     r8d, r8d
0x18018564d  mov     dword ptr [rsp+1F0h+var_1C8], eax
0x180185651  xor     edx, edx
0x180185653  lea     rax, [rbp+0F0h+var_130]
0x180185657  mov     rcx, [rcx+8]
0x18018565b  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x180185660  call    WDICART_IcaChannelInput
0x180185665  mov     ecx, cs:CallbackContext
0x18018566b  cmp     ecx, 5
0x18018566e  jbe     loc_1801852F3
0x180185674  mov     [rbp+0F0h+var_170], eax
0x180185677  lea     rdx, byte_1802A9F25
0x18018567e  lea     rax, aReturnFromKeyb; "Return from keyboard input injection %l"...
0x180185685  mov     [rsp+1F0h+var_180], rax
0x18018568a  lea     rax, [rbp+0F0h+var_170]
0x18018568e  mov     [rsp+1F0h+var_1C8], rax
0x180185693  lea     rax, [rsp+1F0h+var_180]
0x180185698  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x18018569d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801856a2  jmp     loc_1801852F3
0x1801856a7  and     edx, 1Fh; unsigned int
0x1801856aa  mov     rcx, r10; this
0x1801856ad  call    ?IMDoSync@ShareClass@@QEAAJI@Z; ShareClass::IMDoSync(uint)
0x1801856b2  inc     rdi
0x1801856b5  dec     ebx
0x1801856b7  jmp     loc_1801852F3
0x1801856bc  mov     eax, r13d
0x1801856bf  mov     r15d, r9d
0x1801856c2  sub     eax, r14d
0x1801856c5  cmp     eax, r9d
0x1801856c8  cmovb   r15d, eax
0x1801856cc  mov     eax, cs:dword_1802BB170
0x1801856d2  cmp     eax, 5
0x1801856d5  jbe     short loc_180185717
  ... truncated ...
```
