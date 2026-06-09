# IkeDetermineQMPathIkeV2

- ea: `0x1800c4ef0`
- end: `0x1800c5375`
- name: `IkeDetermineQMPathIkeV2`
- size: `1157`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800c4c6c`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180008388`
- `0x1800087f0`
- `0x180024820`
- `0x180025d88`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x1800c4ef0`
- `0x1800c6700`
- `0x1800c6754`
- `0x1800e9034`
- `0x1800f9600`

## import_xrefs

- `WS2_32!__imp_ntohl` at `0x1800c4fb8`
- `WS2_32!__imp_ntohl` at `0x1800c5114`
- `WS2_32!__imp_ntohl` at `0x1800c4fb8`
- `WS2_32!__imp_ntohl` at `0x1800c5114`

## string_xrefs

- `0x1800c506e`: `IKEv2 ENCRYPT FRAGMENT PAYLOAD Received in Quick Mode Negotiation.             Setting path as PROCESS_PATH_FRAG`
- `0x1800c4f25`: `IkeDetermineQMPathIkeV2`
- `0x1800c5333`: `IkeDetermineQMPathIkeV2`
- `0x1800c533f`: `IkeDetermineQMPathIkeV2`
- `0x1800c51b3`: `Switching to INPLACE_REKEY path`

## pseudocode

```c
__int64 __fastcall IkeDetermineQMPathIkeV2(__int64 a1, __int64 *a2, _DWORD *a3)
{
  __int64 IsNewQMSAAllowed; // r15
  __int64 v7; // rbx
  _BYTE *v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rcx
  u_long v11; // edi
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  _UNKNOWN **v25; // rdx
  __int64 v26; // rcx
  u_long v27; // eax
  __int64 v28; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  int TlsMmLuid; // eax
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  _DWORD *v43; // r14
  __int64 v44; // rdi
  __int64 v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  __int64 v49; // r9
  int v50; // eax
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 v56; // [rsp+30h] [rbp-69h] BYREF
  __int64 v57; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v58[2]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v59[32]; // [rsp+50h] [rbp-49h] BYREF
  __int64 *v60; // [rsp+70h] [rbp-29h]
  __int64 v61; // [rsp+78h] [rbp-21h]
  _BYTE v62[16]; // [rsp+80h] [rbp-19h] BYREF
  const char *v63; // [rsp+90h] [rbp-9h]
  __int64 v64; // [rsp+98h] [rbp-1h]
  __int64 *v65; // [rsp+A0h] [rbp+7h]
  __int64 v66; // [rsp+A8h] [rbp+Fh]

  LODWORD(v57) = 0;
  LODWORD(v56) = 0;
  IsNewQMSAAllowed = 0;
  TraceLogHelper("IkeDetermineQMPathIkeV2", 1);
  if ( (unsigned int)IkeIsIkeV2QmPacketDupe(a1, a2) )
  {
    a3[4] = 3;
  }
  else if ( IkeFindPayloadInPacket(a2, 41, &v56)
         || (*(_BYTE *)(*a2 + 19) & 0x20) == 0
         || (v56 = 0, IsNewQMSAAllowed = IkeCopyIncomingData(&v56), NtohTransformIkeV2(&v56), HIWORD(v56) > 0x3FFFu) )
  {
    v7 = *a2;
    v8 = (_BYTE *)(*a2 + 19);
    v11 = ntohl(*(_DWORD *)(*a2 + 20));
    if ( *(_BYTE *)(v7 + 16) != 53 || (*v8 & 4) != 0 )
    {
      v25 = &WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(a1 + 592) & 1) != 0 && (*v8 & 0x20) != 0 && *(_DWORD *)(*(_QWORD *)(a1 + 616) + 4LL) == 6 )
      {
        v26 = *(_QWORD *)(a1 + 976);
        if ( v26 )
        {
          if ( !*(_DWORD *)(v26 + 100) )
          {
            v27 = *(_DWORD *)(*(_QWORD *)(v26 + 296) + 20LL);
            if ( (*(_BYTE *)(v26 + 324) & 2) == 0 )
            {
              v27 = ntohl(v27);
              v25 = &WPP_GLOBAL_Control;
            }
            if ( v11 == v27 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                v28 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                TlsPeerAddr = IkeGetTlsPeerAddr(v26);
                TlsMmLuid = IkeGetTlsMmLuid(v31, v30, v32, v33);
                WPP_SF_iS(
                  v28,
                  21,
                  (unsigned int)WPP_caf746ea5eb1363761fbc4e0554aaa8f_Traceguids,
                  TlsMmLuid,
                  TlsPeerAddr);
              }
              if ( (unsigned int)dword_180173278 > 4 )
              {
                v56 = IkeGetTlsMmLuid(v26, v25, v12, v13);
                v60 = &v56;
                v61 = 8;
                v36 = IkeGetTlsPeerAddr(v35);
                tlgCreate1Sz_wchar_t(v62, v36);
                v64 = 32;
                v65 = v58;
                v63 = "Switching to INPLACE_REKEY path";
                v58[0] = a1;
                v66 = 8;
                tlgWriteTransfer_EtwEventWriteTransfer(
                  (__int64)&dword_180173278,
                  (unsigned __int8 *)&dword_18015C084,
                  v37,
                  v38,
                  6,
                  (__int64)v59);
              }
              a3[1] |= 1u;
              a3[4] = 5;
            }
          }
        }
      }
      IsNewQMSAAllowed = IkeCheckForMMSAIkeV2(a2, &v57);
      if ( !IsNewQMSAAllowed )
      {
        if ( (_DWORD)v57 )
          a3[4] = 5;
        if ( *a3 )
        {
          if ( (*v8 & 0x20) == 0 || (v43 = a3 + 4, a3[4] == 5) )
          {
            IsNewQMSAAllowed = IkeIsNewQMSAAllowed(a1, a2, a3);
            v43 = a3 + 4;
            if ( IsNewQMSAAllowed )
              goto LABEL_49;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v44 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              v45 = IkeGetTlsPeerAddr(v40);
              v50 = IkeGetTlsMmLuid(v47, v46, v48, v49);
              WPP_SF_iS(v44, 22, (unsigned int)WPP_caf746ea5eb1363761fbc4e0554aaa8f_Traceguids, v50, v45);
            }
            if ( (unsigned int)dword_180173278 > 4 )
            {
              v58[0] = IkeGetTlsMmLuid(v40, v39, v41, v42);
              v60 = v58;
              v61 = 8;
              v52 = IkeGetTlsPeerAddr(v51);
              tlgCreate1Sz_wchar_t(v62, v52);
              v64 = 38;
              v63 = "Received new QM as response. Dropping";
              tlgWriteTransfer_EtwEventWriteTransfer(
                (__int64)&dword_180173278,
                (unsigned __int8 *)qword_18015C008,
                v53,
                v54,
                5,
                (__int64)v59);
            }
            a3[1] |= 8u;
            *v43 = 4;
          }
        }
        else
        {
          v43 = a3 + 4;
        }
        if ( !*v43 )
          *v43 = 1;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v15 = IkeGetTlsPeerAddr(v10);
        v20 = IkeGetTlsMmLuid(v17, v16, v18, v19);
        WPP_SF_iSq(v14, 20, (unsigned int)WPP_caf746ea5eb1363761fbc4e0554aaa8f_Traceguids, v20, v15, a1);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v56 = IkeGetTlsMmLuid(v10, v9, v12, v13);
        v60 = &v56;
        v61 = 8;
        v22 = IkeGetTlsPeerAddr(v21);
        tlgCreate1Sz_wchar_t(v62, v22);
        v64 = 113;
        v65 = &v57;
        v63 = "IKEv2 ENCRYPT FRAGMENT PAYLOAD Received in Quick Mode Negotiation.             Setting path as PROCESS_PATH_FRAG";
        v57 = a1;
        v66 = 8;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)byte_18015C043,
          v23,
          v24,
          6,
          (__int64)v59);
      }
      a3[4] = 2;
    }
  }
  else
  {
    a3[4] = 6;
  }
LABEL_49:
  TraceLogHelper("IkeDetermineQMPathIkeV2", 0);
  return IkeReturnError(IsNewQMSAAllowed, "IkeDetermineQMPathIkeV2");
}

```

## disassembly

```asm
0x1800c4ef0  mov     [rsp-8+arg_18], rbx
0x1800c4ef5  push    rbp
0x1800c4ef6  push    rsi
0x1800c4ef7  push    rdi
0x1800c4ef8  push    r12
0x1800c4efa  push    r13
0x1800c4efc  push    r14
0x1800c4efe  push    r15
0x1800c4f00  lea     rbp, [rsp-27h]
0x1800c4f05  sub     rsp, 0C0h
0x1800c4f0c  mov     rax, cs:__security_cookie
0x1800c4f13  xor     rax, rsp
0x1800c4f16  mov     [rbp+57h+var_40], rax
0x1800c4f1a  xor     ebx, ebx
0x1800c4f1c  mov     r12, rdx
0x1800c4f1f  mov     r13, rcx
0x1800c4f22  mov     dword ptr [rbp+57h+var_B8], ebx
0x1800c4f25  lea     rcx, aIkedetermineqm; "IkeDetermineQMPathIkeV2"
0x1800c4f2c  mov     dword ptr [rbp+57h+var_C0], ebx
0x1800c4f2f  mov     rsi, r8
0x1800c4f32  mov     r15d, ebx
0x1800c4f35  lea     edx, [rbx+1]
0x1800c4f38  call    TraceLogHelper
0x1800c4f3d  mov     rdx, r12
0x1800c4f40  mov     rcx, r13
0x1800c4f43  call    IkeIsIkeV2QmPacketDupe
0x1800c4f48  test    eax, eax
0x1800c4f4a  jz      short loc_1800C4F58
0x1800c4f4c  mov     dword ptr [rsi+10h], 3
0x1800c4f53  jmp     loc_1800C5331
0x1800c4f58  mov     edx, 29h ; ')'
0x1800c4f5d  lea     r8, [rbp+57h+var_C0]
0x1800c4f61  mov     rcx, r12
0x1800c4f64  call    IkeFindPayloadInPacket
0x1800c4f69  test    rax, rax
0x1800c4f6c  jnz     short loc_1800C4FB1
0x1800c4f6e  mov     rax, [r12]
0x1800c4f72  test    byte ptr [rax+13h], 20h
0x1800c4f76  jz      short loc_1800C4FB1
0x1800c4f78  mov     r8d, 8
0x1800c4f7e  mov     [rbp+57h+var_C0], rbx
0x1800c4f82  mov     rdx, r12
0x1800c4f85  lea     rcx, [rbp+57h+var_C0]; void *
0x1800c4f89  call    IkeCopyIncomingData
0x1800c4f8e  lea     rcx, [rbp+57h+var_C0]
0x1800c4f92  mov     r15, rax
0x1800c4f95  call    NtohTransformIkeV2
0x1800c4f9a  mov     eax, 3FFFh
0x1800c4f9f  cmp     word ptr [rbp+57h+var_C0+6], ax
0x1800c4fa3  ja      short loc_1800C4FB1
0x1800c4fa5  mov     dword ptr [rsi+10h], 6
0x1800c4fac  jmp     loc_1800C5331
0x1800c4fb1  mov     rbx, [r12]
0x1800c4fb5  mov     ecx, [rbx+14h]; netlong
0x1800c4fb8  call    cs:__imp_ntohl
0x1800c4fbe  cmp     byte ptr [rbx+10h], 35h ; '5'
0x1800c4fc2  lea     r14, [rbx+13h]
0x1800c4fc6  mov     edi, eax
0x1800c4fc8  jnz     loc_1800C50B5
0x1800c4fce  test    byte ptr [r14], 4
0x1800c4fd2  jnz     loc_1800C50B5
0x1800c4fd8  mov     rdi, cs:WPP_GLOBAL_Control
0x1800c4fdf  lea     rax, WPP_GLOBAL_Control
0x1800c4fe6  cmp     rdi, rax
0x1800c4fe9  jz      short loc_1800C5029
0x1800c4feb  cmp     byte ptr [rdi+19h], 4
0x1800c4fef  jb      short loc_1800C5029
0x1800c4ff1  test    byte ptr [rdi+1Ch], 10h
0x1800c4ff5  jz      short loc_1800C5029
0x1800c4ff7  mov     rdi, [rdi+10h]
0x1800c4ffb  call    IkeGetTlsPeerAddr
0x1800c5000  mov     rbx, rax
0x1800c5003  call    IkeGetTlsMmLuid
0x1800c5008  mov     r9, rax
0x1800c500b  mov     [rsp+0F0h+var_C8], r13
0x1800c5010  mov     edx, 14h
0x1800c5015  mov     [rsp+0F0h+var_D0], rbx
0x1800c501a  lea     r8, WPP_caf746ea5eb1363761fbc4e0554aaa8f_Traceguids
0x1800c5021  mov     rcx, rdi
0x1800c5024  call    WPP_SF_iSq
0x1800c5029  mov     eax, cs:dword_180173278
0x1800c502f  cmp     eax, 4
0x1800c5032  jbe     short loc_1800C50A9
0x1800c5034  call    IkeGetTlsMmLuid
0x1800c5039  mov     [rbp+57h+var_C0], rax
0x1800c503d  lea     rax, [rbp+57h+var_C0]
0x1800c5041  mov     [rbp+57h+var_80], rax
0x1800c5045  mov     [rbp+57h+var_78], 8
0x1800c504d  call    IkeGetTlsPeerAddr
0x1800c5052  mov     rdx, rax
0x1800c5055  lea     rcx, [rbp+57h+var_70]
0x1800c5059  call    _tlgCreate1Sz_wchar_t
0x1800c505e  lea     rax, [rbp+57h+var_B8]
0x1800c5062  mov     [rbp+57h+var_58], 71h ; 'q'
0x1800c506a  mov     [rbp+57h+var_50], rax
0x1800c506e  lea     rcx, aIkev2EncryptFr_0; "IKEv2 ENCRYPT FRAGMENT PAYLOAD Received"...
0x1800c5075  lea     rax, [rbp+57h+var_A0]
0x1800c5079  mov     [rbp+57h+var_60], rcx
0x1800c507d  mov     [rsp+0F0h+var_C8], rax
0x1800c5082  lea     rdx, byte_18015C043
0x1800c5089  lea     rcx, dword_180173278
0x1800c5090  mov     dword ptr [rsp+0F0h+var_D0], 6
0x1800c5098  mov     [rbp+57h+var_B8], r13
0x1800c509c  mov     [rbp+57h+var_48], 8
0x1800c50a4  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800c50a9  mov     dword ptr [rsi+10h], 2
0x1800c50b0  jmp     loc_1800C5331
0x1800c50b5  test    byte ptr [r13+250h], 1
0x1800c50bd  lea     rdx, WPP_GLOBAL_Control
0x1800c50c4  jz      loc_1800C51F9
0x1800c50ca  test    byte ptr [r14], 20h
0x1800c50ce  jz      loc_1800C51F9
0x1800c50d4  mov     rax, [r13+268h]
0x1800c50db  cmp     dword ptr [rax+4], 6
0x1800c50df  jnz     loc_1800C51F9
0x1800c50e5  mov     rcx, [r13+3D0h]
0x1800c50ec  test    rcx, rcx
0x1800c50ef  jz      loc_1800C51F9
0x1800c50f5  cmp     dword ptr [rcx+64h], 0
0x1800c50f9  jnz     loc_1800C51F9
0x1800c50ff  test    byte ptr [rcx+144h], 2
0x1800c5106  mov     rax, [rcx+128h]
0x1800c510d  mov     eax, [rax+14h]
0x1800c5110  jnz     short loc_1800C5121
0x1800c5112  mov     ecx, eax; netlong
0x1800c5114  call    cs:__imp_ntohl
0x1800c511a  lea     rdx, WPP_GLOBAL_Control
0x1800c5121  cmp     edi, eax
0x1800c5123  jnz     loc_1800C51F9
0x1800c5129  mov     rdi, cs:WPP_GLOBAL_Control
0x1800c5130  cmp     rdi, rdx
0x1800c5133  jz      short loc_1800C516E
0x1800c5135  cmp     byte ptr [rdi+19h], 4
0x1800c5139  jb      short loc_1800C516E
0x1800c513b  test    byte ptr [rdi+1Ch], 10h
0x1800c513f  jz      short loc_1800C516E
0x1800c5141  mov     rdi, [rdi+10h]
0x1800c5145  call    IkeGetTlsPeerAddr
0x1800c514a  mov     rbx, rax
0x1800c514d  call    IkeGetTlsMmLuid
0x1800c5152  mov     r9, rax
0x1800c5155  mov     [rsp+0F0h+var_D0], rbx
0x1800c515a  mov     edx, 15h
0x1800c515f  lea     r8, WPP_caf746ea5eb1363761fbc4e0554aaa8f_Traceguids
0x1800c5166  mov     rcx, rdi
0x1800c5169  call    WPP_SF_iS
0x1800c516e  mov     eax, cs:dword_180173278
0x1800c5174  cmp     eax, 4
0x1800c5177  jbe     short loc_1800C51EE
0x1800c5179  call    IkeGetTlsMmLuid
0x1800c517e  mov     [rbp+57h+var_C0], rax
0x1800c5182  lea     rax, [rbp+57h+var_C0]
0x1800c5186  mov     [rbp+57h+var_80], rax
0x1800c518a  mov     [rbp+57h+var_78], 8
0x1800c5192  call    IkeGetTlsPeerAddr
0x1800c5197  mov     rdx, rax
0x1800c519a  lea     rcx, [rbp+57h+var_70]
0x1800c519e  call    _tlgCreate1Sz_wchar_t
0x1800c51a3  lea     rax, [rbp+57h+var_B0]
0x1800c51a7  mov     [rbp+57h+var_58], 20h ; ' '
0x1800c51af  mov     [rbp+57h+var_50], rax
0x1800c51b3  lea     rcx, aSwitchingToInp; "Switching to INPLACE_REKEY path"
0x1800c51ba  lea     rax, [rbp+57h+var_A0]
0x1800c51be  mov     [rbp+57h+var_60], rcx
0x1800c51c2  mov     [rsp+0F0h+var_C8], rax
0x1800c51c7  lea     rdx, dword_18015C084
0x1800c51ce  lea     rcx, dword_180173278
0x1800c51d5  mov     dword ptr [rsp+0F0h+var_D0], 6
0x1800c51dd  mov     [rbp+57h+var_B0], r13
0x1800c51e1  mov     [rbp+57h+var_48], 8
0x1800c51e9  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800c51ee  or      dword ptr [rsi+4], 1
0x1800c51f2  mov     dword ptr [rsi+10h], 5
0x1800c51f9  lea     rdx, [rbp+57h+var_B8]
0x1800c51fd  mov     rcx, r12
0x1800c5200  call    IkeCheckForMMSAIkeV2
0x1800c5205  mov     r15, rax
0x1800c5208  test    rax, rax
0x1800c520b  jnz     loc_1800C5331
0x1800c5211  lea     rbx, [rsi+10h]
0x1800c5215  cmp     dword ptr [rbp+57h+var_B8], eax
0x1800c5218  jz      short loc_1800C5220
0x1800c521a  mov     dword ptr [rbx], 5
0x1800c5220  cmp     dword ptr [rsi], 0
0x1800c5223  jz      loc_1800C5321
0x1800c5229  test    byte ptr [r14], 20h
0x1800c522d  jz      loc_1800C5306
0x1800c5233  lea     r14, [rsi+10h]
0x1800c5237  cmp     dword ptr [r14], 5
0x1800c523b  jz      loc_1800C5306
0x1800c5241  mov     rdi, cs:WPP_GLOBAL_Control
0x1800c5248  lea     rax, WPP_GLOBAL_Control
0x1800c524f  cmp     rdi, rax
0x1800c5252  jz      short loc_1800C528D
0x1800c5254  cmp     byte ptr [rdi+19h], 4
0x1800c5258  jb      short loc_1800C528D
0x1800c525a  test    byte ptr [rdi+1Ch], 10h
0x1800c525e  jz      short loc_1800C528D
0x1800c5260  mov     rdi, [rdi+10h]
0x1800c5264  call    IkeGetTlsPeerAddr
0x1800c5269  mov     rbx, rax
0x1800c526c  call    IkeGetTlsMmLuid
0x1800c5271  mov     r9, rax
0x1800c5274  mov     [rsp+0F0h+var_D0], rbx
0x1800c5279  mov     edx, 16h
0x1800c527e  lea     r8, WPP_caf746ea5eb1363761fbc4e0554aaa8f_Traceguids
0x1800c5285  mov     rcx, rdi
0x1800c5288  call    WPP_SF_iS
0x1800c528d  mov     eax, cs:dword_180173278
0x1800c5293  cmp     eax, 4
0x1800c5296  jbe     short loc_1800C52F9
0x1800c5298  call    IkeGetTlsMmLuid
0x1800c529d  mov     [rbp+57h+var_B0], rax
0x1800c52a1  lea     rax, [rbp+57h+var_B0]
0x1800c52a5  mov     [rbp+57h+var_80], rax
0x1800c52a9  mov     [rbp+57h+var_78], 8
0x1800c52b1  call    IkeGetTlsPeerAddr
0x1800c52b6  mov     rdx, rax
0x1800c52b9  lea     rcx, [rbp+57h+var_70]
0x1800c52bd  call    _tlgCreate1Sz_wchar_t
0x1800c52c2  lea     rcx, aReceivedNewQmA; "Received new QM as response. Dropping"
0x1800c52c9  mov     [rbp+57h+var_58], 26h ; '&'
0x1800c52d1  lea     rax, [rbp+57h+var_A0]
0x1800c52d5  mov     [rbp+57h+var_60], rcx
0x1800c52d9  mov     [rsp+0F0h+var_C8], rax
0x1800c52de  lea     rcx, dword_180173278
0x1800c52e5  lea     rdx, qword_18015C008
0x1800c52ec  mov     dword ptr [rsp+0F0h+var_D0], 5
0x1800c52f4  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800c52f9  or      dword ptr [rsi+4], 8
0x1800c52fd  mov     dword ptr [r14], 4
0x1800c5304  jmp     short loc_1800C5324
0x1800c5306  mov     r8, rsi
0x1800c5309  mov     rdx, r12
0x1800c530c  mov     rcx, r13
0x1800c530f  call    IkeIsNewQMSAAllowed
0x1800c5314  mov     r15, rax
0x1800c5317  mov     r14, rbx
0x1800c531a  test    rax, rax
0x1800c531d  jnz     short loc_1800C5331
0x1800c531f  jmp     short loc_1800C5324
0x1800c5321  mov     r14, rbx
0x1800c5324  cmp     dword ptr [r14], 0
0x1800c5328  jnz     short loc_1800C5331
0x1800c532a  mov     dword ptr [r14], 1
0x1800c5331  xor     edx, edx
0x1800c5333  lea     rcx, aIkedetermineqm; "IkeDetermineQMPathIkeV2"
0x1800c533a  call    TraceLogHelper
0x1800c533f  lea     rdx, aIkedetermineqm; "IkeDetermineQMPathIkeV2"
0x1800c5346  mov     rcx, r15
0x1800c5349  call    IkeReturnError
0x1800c534e  mov     rcx, [rbp+57h+var_40]
0x1800c5352  xor     rcx, rsp; StackCookie
0x1800c5355  call    __security_check_cookie
0x1800c535a  mov     rbx, [rsp+0F0h+arg_18]
0x1800c5362  add     rsp, 0C0h
0x1800c5369  pop     r15
0x1800c536b  pop     r14
0x1800c536d  pop     r13
0x1800c536f  pop     r12
0x1800c5371  pop     rdi
0x1800c5372  pop     rsi
0x1800c5373  pop     rbp
0x1800c5374  retn
```
