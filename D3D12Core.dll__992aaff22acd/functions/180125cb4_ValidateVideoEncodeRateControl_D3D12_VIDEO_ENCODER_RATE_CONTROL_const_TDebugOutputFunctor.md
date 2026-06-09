# ValidateVideoEncodeRateControl(D3D12_VIDEO_ENCODER_RATE_CONTROL const &,TDebugOutputFunctor &)

- ea: `0x180125cb4`
- end: `0x180125ee6`
- name: `?ValidateVideoEncodeRateControl@@YAJAEBUD3D12_VIDEO_ENCODER_RATE_CONTROL@@AEAUTDebugOutputFunctor@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(const struct D3D12_VIDEO_ENCODER_RATE_CONTROL *, struct TDebugOutputFunctor *)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b015c`
- `0x180120f6c`
- `0x180121330`
- `0x18012189c`
- `0x1802404b4`
- `0x180246e70`

## callees

- `0x18002ef50`
- `0x180125cb4`

## string_xrefs

- `0x180125eb4`: `The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_AbsoluteQPMap. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP Expected size: %d Received size: %d`
- `0x180125e42`: `The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_CQP cannot be null.`
- `0x180125cf3`: `The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.Flags must be a valid combination of D3D12_VIDEO_ENCODER_RATE_CONTROL_FLAGS values.`
- `0x180125e93`: `The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_AbsoluteQPMap cannot be null.`
- `0x180125dbb`: `The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_VBR1. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_VBR1 Expected size: %d Received size: %d`
- `0x180125dd6`: `The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_VBR. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_VBR Expected size: %d Received size: %d`
- `0x180125e2f`: `The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_CBR. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_CBR Expected size: %d Received size: %d`
- `0x180125d90`: `The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_VBR cannot be null.`
- `0x180125de9`: `The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_CBR cannot be null.`
- `0x180125e14`: `The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_CBR1. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_CBR1 Expected size: %d Received size: %d`
- `0x180125e69`: `The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_CQP1. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_CQP1 Expected size: %d Received size: %d`
- `0x180125e7d`: `The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_CQP. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_CQP Expected size: %d Received size: %d`
- `0x180125d7d`: `The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_QVBR. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_QVBR Expected size: %d Received size: %d`
- `0x180125d62`: `The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_QVBR1. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_QVBR1 Expected size: %d Received size: %d`
- `0x180125d37`: `The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_QVBR/pConfiguration_QVBR1 cannot be null.`

## pseudocode

```c
__int64 __fastcall ValidateVideoEncodeRateControl(
        const struct D3D12_VIDEO_ENCODER_RATE_CONTROL *a1,
        struct TDebugOutputFunctor *a2)
{
  char v4; // cl
  int v5; // eax
  const char *v6; // r8
  int v7; // eax
  int v8; // eax
  int v9; // eax

  if ( *(int *)a1 >= 5 )
  {
    TDebugOutputFunctor::operator()(
      a2,
      1305,
      "The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.Mode must be a valid value of D3D12_VIDEO_ENCODER_RATE_CONTROL_MODE.");
    v4 = 0;
  }
  else
  {
    v4 = 1;
  }
  if ( (*((_DWORD *)a1 + 1) & 0xFFFFFE00) != 0 )
  {
    TDebugOutputFunctor::operator()(
      a2,
      1305,
      "The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.Flags must be a valid combination of D3D12_VIDEO_ENCODER_RATE_CONTROL_FLAGS values.");
    v4 = 0;
  }
  if ( *(_DWORD *)a1 )
  {
    switch ( *(_DWORD *)a1 )
    {
      case 1:
        if ( !*((_QWORD *)a1 + 2) )
        {
          TDebugOutputFunctor::operator()(
            a2,
            1305,
            "The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_CQP cannot be null.");
          v4 = 0;
        }
        v9 = *((_DWORD *)a1 + 2);
        if ( (*((_BYTE *)a1 + 4) & 0x40) != 0 )
        {
          if ( v9 != 16 )
          {
            v6 = "The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_C"
                 "QP1. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_CQP1 Expected size: %d Received size: %d";
            goto LABEL_44;
          }
        }
        else if ( v9 != 12 )
        {
          v6 = "The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_CQP"
               ". does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_CQP Expected size: %d Received size: %d";
          goto LABEL_44;
        }
        break;
      case 2:
        if ( !*((_QWORD *)a1 + 2) )
        {
          TDebugOutputFunctor::operator()(
            a2,
            1305,
            "The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_CBR cannot be null.");
          v4 = 0;
        }
        v8 = *((_DWORD *)a1 + 2);
        if ( (*((_BYTE *)a1 + 4) & 0x40) != 0 )
        {
          if ( v8 != 56 )
          {
            v6 = "The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_C"
                 "BR1. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_CBR1 Expected size: %d Received size: %d";
            goto LABEL_44;
          }
        }
        else if ( v8 != 48 )
        {
          v6 = "The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_CBR"
               ". does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_CBR Expected size: %d Received size: %d";
          goto LABEL_44;
        }
        break;
      case 3:
        if ( !*((_QWORD *)a1 + 2) )
        {
          TDebugOutputFunctor::operator()(
            a2,
            1305,
            "The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_VBR cannot be null.");
          v4 = 0;
        }
        v7 = *((_DWORD *)a1 + 2);
        if ( (*((_BYTE *)a1 + 4) & 0x40) != 0 )
        {
          if ( v7 != 64 )
          {
            v6 = "The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_V"
                 "BR1. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_VBR1 Expected size: %d Received size: %d";
            goto LABEL_44;
          }
        }
        else if ( v7 != 56 )
        {
          v6 = "The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_VBR"
               ". does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_VBR Expected size: %d Received size: %d";
          goto LABEL_44;
        }
        break;
      case 4:
        if ( !*((_QWORD *)a1 + 2) )
        {
          TDebugOutputFunctor::operator()(
            a2,
            1305,
            "The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_QVBR/pConfiguration_QVBR1 cannot be null.");
          v4 = 0;
        }
        v5 = *((_DWORD *)a1 + 2);
        if ( (*((_BYTE *)a1 + 4) & 0x40) != 0 )
        {
          if ( v5 != 72 )
          {
            v6 = "The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_Q"
                 "VBR1. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_QVBR1 Expected size: %d Received size: %d";
LABEL_44:
            TDebugOutputFunctor::operator()(a2, 1305, v6);
            v4 = 0;
          }
        }
        else if ( v5 != 48 )
        {
          v6 = "The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_QVB"
               "R. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_QVBR Expected size: %d Received size: %d";
          goto LABEL_44;
        }
        break;
    }
  }
  else if ( (*((_BYTE *)a1 + 4) & 0x40) != 0 )
  {
    if ( !*((_QWORD *)a1 + 2) )
    {
      TDebugOutputFunctor::operator()(
        a2,
        1305,
        "The value in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_AbsoluteQPMap cannot be null.");
      v4 = 0;
    }
    if ( *((_DWORD *)a1 + 2) != 4 )
    {
      v6 = "The data size of the structure passed in D3D12_VIDEO_ENCODER_RATE_CONTROL.ConfigParams.pConfiguration_Absolut"
           "eQPMap. does not match the expected size of D3D12_VIDEO_ENCODER_RATE_CONTROL_ABSOLUTE_QP_MAP Expected size: %"
           "d Received size: %d";
      goto LABEL_44;
    }
  }
  return v4 == 0 ? 0x80070057 : 0;
}

```

## disassembly

```asm
0x180125cb4  mov     [rsp+arg_0], rbx
0x180125cb9  mov     [rsp+arg_8], rbp
0x180125cbe  push    rdi
0x180125cbf  sub     rsp, 30h
0x180125cc3  cmp     dword ptr [rcx], 5
0x180125cc6  mov     rdi, rdx
0x180125cc9  mov     rbx, rcx
0x180125ccc  mov     ebp, 519h
0x180125cd1  jge     short loc_180125CD7
0x180125cd3  mov     cl, 1
0x180125cd5  jmp     short loc_180125CEA
0x180125cd7  lea     r8, aTheValueInD3d1_3; "The value in D3D12_VIDEO_ENCODER_RATE_C"...
0x180125cde  mov     edx, ebp
0x180125ce0  mov     rcx, rdi
0x180125ce3  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125ce8  xor     cl, cl
0x180125cea  test    dword ptr [rbx+4], 0FFFFFE00h
0x180125cf1  jz      short loc_180125D06
0x180125cf3  lea     r8, aTheValueInD3d1_4; "The value in D3D12_VIDEO_ENCODER_RATE_C"...
0x180125cfa  mov     edx, ebp
0x180125cfc  mov     rcx, rdi
0x180125cff  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125d04  xor     cl, cl
0x180125d06  mov     edx, [rbx]
0x180125d08  test    edx, edx
0x180125d0a  jz      loc_180125E86
0x180125d10  sub     edx, 1
0x180125d13  jz      loc_180125E3B
0x180125d19  sub     edx, 1
0x180125d1c  jz      loc_180125DE2
0x180125d22  sub     edx, 1
0x180125d25  jz      short loc_180125D89
0x180125d27  cmp     edx, 1
0x180125d2a  jnz     loc_180125ECB
0x180125d30  cmp     qword ptr [rbx+10h], 0
0x180125d35  jnz     short loc_180125D4A
0x180125d37  lea     r8, aTheValueInD3d1_1; "The value in D3D12_VIDEO_ENCODER_RATE_C"...
0x180125d3e  mov     edx, ebp
0x180125d40  mov     rcx, rdi
0x180125d43  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125d48  xor     cl, cl
0x180125d4a  test    byte ptr [rbx+4], 40h
0x180125d4e  mov     eax, [rbx+8]
0x180125d51  jz      short loc_180125D6E
0x180125d53  mov     r9d, 48h ; 'H'
0x180125d59  cmp     eax, r9d
0x180125d5c  jz      loc_180125ECB
0x180125d62  lea     r8, aTheDataSizeOfT_4; "The data size of the structure passed i"...
0x180125d69  jmp     loc_180125EBB
0x180125d6e  cmp     eax, 30h ; '0'
0x180125d71  jz      loc_180125ECB
0x180125d77  mov     r9d, 30h ; '0'
0x180125d7d  lea     r8, aTheDataSizeOfT_5; "The data size of the structure passed i"...
0x180125d84  jmp     loc_180125EBB
0x180125d89  cmp     qword ptr [rbx+10h], 0
0x180125d8e  jnz     short loc_180125DA3
0x180125d90  lea     r8, aTheValueInD3d1; "The value in D3D12_VIDEO_ENCODER_RATE_C"...
0x180125d97  mov     edx, ebp
0x180125d99  mov     rcx, rdi
0x180125d9c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125da1  xor     cl, cl
0x180125da3  test    byte ptr [rbx+4], 40h
0x180125da7  mov     eax, [rbx+8]
0x180125daa  jz      short loc_180125DC7
0x180125dac  cmp     eax, 40h ; '@'
0x180125daf  jz      loc_180125ECB
0x180125db5  mov     r9d, 40h ; '@'
0x180125dbb  lea     r8, aTheDataSizeOfT_13; "The data size of the structure passed i"...
0x180125dc2  jmp     loc_180125EBB
0x180125dc7  cmp     eax, 38h ; '8'
0x180125dca  jz      loc_180125ECB
0x180125dd0  mov     r9d, 38h ; '8'
0x180125dd6  lea     r8, aTheDataSizeOfT_1; "The data size of the structure passed i"...
0x180125ddd  jmp     loc_180125EBB
0x180125de2  cmp     qword ptr [rbx+10h], 0
0x180125de7  jnz     short loc_180125DFC
0x180125de9  lea     r8, aTheValueInD3d1_5; "The value in D3D12_VIDEO_ENCODER_RATE_C"...
0x180125df0  mov     edx, ebp
0x180125df2  mov     rcx, rdi
0x180125df5  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125dfa  xor     cl, cl
0x180125dfc  test    byte ptr [rbx+4], 40h
0x180125e00  mov     eax, [rbx+8]
0x180125e03  jz      short loc_180125E20
0x180125e05  cmp     eax, 38h ; '8'
0x180125e08  jz      loc_180125ECB
0x180125e0e  mov     r9d, 38h ; '8'
0x180125e14  lea     r8, aTheDataSizeOfT; "The data size of the structure passed i"...
0x180125e1b  jmp     loc_180125EBB
0x180125e20  cmp     eax, 30h ; '0'
0x180125e23  jz      loc_180125ECB
0x180125e29  mov     r9d, 30h ; '0'
0x180125e2f  lea     r8, aTheDataSizeOfT_2; "The data size of the structure passed i"...
0x180125e36  jmp     loc_180125EBB
0x180125e3b  cmp     qword ptr [rbx+10h], 0
0x180125e40  jnz     short loc_180125E55
0x180125e42  lea     r8, aTheValueInD3d1_0; "The value in D3D12_VIDEO_ENCODER_RATE_C"...
0x180125e49  mov     edx, ebp
0x180125e4b  mov     rcx, rdi
0x180125e4e  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125e53  xor     cl, cl
0x180125e55  test    byte ptr [rbx+4], 40h
0x180125e59  mov     eax, [rbx+8]
0x180125e5c  jz      short loc_180125E72
0x180125e5e  mov     r9d, 10h
0x180125e64  cmp     eax, r9d
0x180125e67  jz      short loc_180125ECB
0x180125e69  lea     r8, aTheDataSizeOfT_11; "The data size of the structure passed i"...
0x180125e70  jmp     short loc_180125EBB
0x180125e72  mov     r9d, 0Ch
0x180125e78  cmp     eax, r9d
0x180125e7b  jz      short loc_180125ECB
0x180125e7d  lea     r8, aTheDataSizeOfT_3; "The data size of the structure passed i"...
0x180125e84  jmp     short loc_180125EBB
0x180125e86  test    byte ptr [rbx+4], 40h
0x180125e8a  jz      short loc_180125ECB
0x180125e8c  cmp     qword ptr [rbx+10h], 0
0x180125e91  jnz     short loc_180125EA6
0x180125e93  lea     r8, aTheValueInD3d1_2; "The value in D3D12_VIDEO_ENCODER_RATE_C"...
0x180125e9a  mov     edx, ebp
0x180125e9c  mov     rcx, rdi
0x180125e9f  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125ea4  xor     cl, cl
0x180125ea6  mov     eax, [rbx+8]
0x180125ea9  mov     r9d, 4
0x180125eaf  cmp     eax, r9d
0x180125eb2  jz      short loc_180125ECB
0x180125eb4  lea     r8, aTheDataSizeOfT_6; "The data size of the structure passed i"...
0x180125ebb  mov     edx, ebp
0x180125ebd  mov     [rsp+38h+var_18], eax
0x180125ec1  mov     rcx, rdi
0x180125ec4  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180125ec9  xor     cl, cl
0x180125ecb  mov     rbx, [rsp+38h+arg_0]
0x180125ed0  neg     cl
0x180125ed2  mov     rbp, [rsp+38h+arg_8]
0x180125ed7  sbb     eax, eax
0x180125ed9  not     eax
0x180125edb  and     eax, 80070057h
0x180125ee0  add     rsp, 30h
0x180125ee4  pop     rdi
0x180125ee5  retn
```
