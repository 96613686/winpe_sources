# Rdp::Avenc::Yuv::CYuvProcessor::OnCreateFrameProcessor(_GUID const &,unsigned __int64,bool)

- ea: `0x18005af04`
- end: `0x18005b154`
- name: `?OnCreateFrameProcessor@CYuvProcessor@Yuv@Avenc@Rdp@@QEAAXAEBU_GUID@@_K_N@Z`
- size: `592`
- prototype: `void __fastcall(Rdp::Avenc::Yuv::CYuvProcessor *__hidden this, const struct _GUID *, unsigned __int64, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180060bd0`

## callees

- `0x180001114`
- `0x180006580`
- `0x1800103c0`
- `0x180010bc8`
- `0x18001143c`
- `0x180022e44`
- `0x180023ee4`
- `0x18005af04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005b109`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005b109`

## string_xrefs

- `0x18005afca`: `OnCreateFrameProcessor`
- `0x18005afdd`: `Rdp::Avenc::Yuv::CYuvProcessor::OnCreateFrameProcessor`
- `0x18005b0a4`: `Unable to ensure RDPCTRL_SRC_CREATE_FRAME_PROCESSOR`
- `0x18005b0bb`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpCtrl/RdpCtrl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Avenc::Yuv::CYuvProcessor::OnCreateFrameProcessor(
        Rdp::Avenc::CFcWireEncoder **this,
        const struct _GUID *a2,
        __int64 a3,
        unsigned __int8 a4)
{
  int v4; // r14d
  char *v8; // rbx
  Rdp::Avenc::CFcWireEncoder *v9; // rcx
  __int64 v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rax
  unsigned int v14; // edx
  int v16; // [rsp+30h] [rbp-89h] BYREF
  int v17; // [rsp+34h] [rbp-85h] BYREF
  _QWORD v18[2]; // [rsp+38h] [rbp-81h] BYREF
  char v19; // [rsp+48h] [rbp-71h]
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+50h] [rbp-69h] BYREF
  const char *v21; // [rsp+70h] [rbp-49h]
  __int64 v22; // [rsp+78h] [rbp-41h]
  int *v23; // [rsp+80h] [rbp-39h]
  __int64 v24; // [rsp+88h] [rbp-31h]
  const char *v25; // [rsp+90h] [rbp-29h]
  __int64 v26; // [rsp+98h] [rbp-21h]
  const char *v27; // [rsp+A0h] [rbp-19h]
  __int64 v28; // [rsp+A8h] [rbp-11h]
  const struct _GUID *v29; // [rsp+B0h] [rbp-9h]
  __int64 v30; // [rsp+B8h] [rbp-1h]
  _QWORD *v31; // [rsp+C0h] [rbp+7h]
  __int64 v32; // [rsp+C8h] [rbp+Fh]
  int *v33; // [rsp+D0h] [rbp+17h]
  __int64 v34; // [rsp+D8h] [rbp+1Fh]
  void *retaddr; // [rsp+118h] [rbp+5Fh]

  v4 = a4;
  if ( this[42] )
  {
    v8 = (char *)(this + 32);
    v18[1] = this + 32;
    v19 = 0;
    if ( (unsigned int)mtx_do_lock((__int64)(this + 32)) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)v8 + 19) == 0x7FFFFFFF )
    {
      *((_DWORD *)v8 + 19) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v19 = 1;
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v17 = v4;
      v18[0] = a3;
      v16 = 511;
      v33 = &v17;
      v34 = 4;
      v31 = v18;
      v32 = 8;
      v29 = a2;
      v30 = 16;
      v27 = "OnCreateFrameProcessor";
      v28 = 23;
      v25 = "Rdp::Avenc::Yuv::CYuvProcessor::OnCreateFrameProcessor";
      v26 = 55;
      v23 = &v16;
      v24 = 4;
      v21 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp";
      v22 = 70;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_1800C1058, (unsigned __int8 *)&word_1800B3E0E, 0, 0, 9u, &v20);
    }
    Rdp::Avenc::CFcWireEncoder::AllocatePool(this[42], 0x1000u, 0, 0);
    v9 = this[42];
    v10 = 0;
    while ( 1 )
    {
      v13 = *((unsigned int *)v9 + 15);
      if ( (unsigned int)v13 >= *((_DWORD *)v9 + 14) )
        break;
      v11 = *((_QWORD *)v9 + 8);
      v12 = *((_QWORD *)v9 + 4);
      if ( (unsigned __int64)(*(_QWORD *)(v12 + 24 * v13 + 8) - v11) >= 0x28 )
      {
        v10 = v11 + *(_QWORD *)(v12 + 24 * v13 + 16);
        *((_QWORD *)v9 + 8) = v11 + 40;
        break;
      }
      *(_QWORD *)(v12 + 24 * v13 + 8) = v11;
      *((_QWORD *)v9 + 8) = 0;
      ++*((_DWORD *)v9 + 15);
    }
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      428,
      "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpCtrl/RdpCtrl.h",
      2147942414LL);
    *(_DWORD *)(v10 + 8) = 1;
    *(_DWORD *)v10 = 40;
    *(struct _GUID *)(v10 + 12) = *a2;
    *(_QWORD *)(v10 + 28) = a3;
    *(_DWORD *)(v10 + 36) = v4;
    Rdp::Avenc::CFcWireEncoder::Flush(this[42], v14);
    if ( (*((_DWORD *)v8 + 19))-- == 1 )
    {
      *((_DWORD *)v8 + 18) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v8 + 2);
    }
  }
}

```

## disassembly

```asm
0x18005af04  mov     [rsp-8+arg_8], rbx
0x18005af09  mov     [rsp-8+arg_10], rsi
0x18005af0e  push    rbp
0x18005af0f  push    rdi
0x18005af10  push    r12
0x18005af12  push    r14
0x18005af14  push    r15
0x18005af16  lea     rbp, [rsp-37h]
0x18005af1b  sub     rsp, 0F0h
0x18005af22  mov     rax, cs:__security_cookie
0x18005af29  xor     rax, rsp
0x18005af2c  mov     [rbp+57h+var_30], rax
0x18005af30  movzx   r14d, r9b
0x18005af34  mov     r15, r8
0x18005af37  mov     r12, rdx
0x18005af3a  mov     rdi, rcx
0x18005af3d  cmp     qword ptr [rcx+150h], 0
0x18005af45  jz      loc_18005B10F
0x18005af4b  lea     rbx, [rcx+100h]
0x18005af52  mov     [rbp+57h+var_D0], rbx
0x18005af56  mov     [rbp+57h+var_C8], 0
0x18005af5a  mov     rcx, rbx
0x18005af5d  call    mtx_do_lock
0x18005af62  test    eax, eax
0x18005af64  jnz     loc_18005B149
0x18005af6a  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18005af71  jz      loc_18005B137
0x18005af77  mov     [rbp+57h+var_C8], 1
0x18005af7b  mov     eax, cs:dword_1800C1058
0x18005af81  cmp     eax, 5
0x18005af84  jbe     loc_18005B03E
0x18005af8a  mov     [rsp+110h+var_DC], r14d
0x18005af8f  mov     [rsp+110h+var_D8], r15
0x18005af94  mov     [rsp+110h+var_E0], 1FFh
0x18005af9c  lea     rax, [rsp+110h+var_DC]
0x18005afa1  mov     [rbp+57h+var_40], rax
0x18005afa5  mov     [rbp+57h+var_38], 4
0x18005afad  lea     rax, [rsp+110h+var_D8]
0x18005afb2  mov     [rbp+57h+var_50], rax
0x18005afb6  mov     [rbp+57h+var_48], 8
0x18005afbe  mov     [rbp+57h+var_60], r12
0x18005afc2  mov     [rbp+57h+var_58], 10h
0x18005afca  lea     rax, aOncreateframep; "OnCreateFrameProcessor"
0x18005afd1  mov     [rbp+57h+var_70], rax
0x18005afd5  mov     [rbp+57h+var_68], 17h
0x18005afdd  lea     rax, aRdpAvencYuvCyu_10; "Rdp::Avenc::Yuv::CYuvProcessor::OnCreat"...
0x18005afe4  mov     [rbp+57h+var_80], rax
0x18005afe8  mov     [rbp+57h+var_78], 37h ; '7'
0x18005aff0  lea     rax, [rsp+110h+var_E0]
0x18005aff5  mov     [rbp+57h+var_90], rax
0x18005aff9  mov     [rbp+57h+var_88], 4
0x18005b001  lea     rax, aOnecoreuapTerm_33; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005b008  mov     [rbp+57h+var_A0], rax
0x18005b00c  mov     [rbp+57h+var_98], 46h ; 'F'
0x18005b014  lea     rax, [rbp+57h+var_C0]
0x18005b018  mov     [rsp+110h+var_E8], rax
0x18005b01d  mov     dword ptr [rsp+110h+var_F0], 9
0x18005b025  xor     r9d, r9d
0x18005b028  xor     r8d, r8d
0x18005b02b  lea     rdx, word_1800B3E0E
0x18005b032  lea     rcx, dword_1800C1058
0x18005b039  call    _tlgWriteTransfer_EventWriteTransfer
0x18005b03e  xor     r9d, r9d; unsigned __int64
0x18005b041  xor     r8d, r8d; unsigned int
0x18005b044  mov     edx, 1000h; unsigned __int64
0x18005b049  mov     rcx, [rdi+150h]; this
0x18005b050  call    ?AllocatePool@CFcWireEncoder@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoder::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x18005b055  mov     rcx, [rdi+150h]
0x18005b05c  xor     esi, esi
0x18005b05e  jmp     short loc_18005B086
0x18005b060  mov     rdx, [rcx+40h]
0x18005b064  lea     r8, [rax+rax*2]
0x18005b068  mov     r9, [rcx+20h]
0x18005b06c  mov     rax, [r9+r8*8+8]
0x18005b071  sub     rax, rdx
0x18005b074  cmp     rax, 28h ; '('
0x18005b078  jnb     short loc_18005B090
0x18005b07a  mov     [r9+r8*8+8], rdx
0x18005b07f  mov     [rcx+40h], rsi
0x18005b083  inc     dword ptr [rcx+3Ch]
0x18005b086  mov     eax, [rcx+3Ch]
0x18005b089  cmp     eax, [rcx+38h]
0x18005b08c  jb      short loc_18005B060
0x18005b08e  jmp     short loc_18005B0A0
0x18005b090  mov     rsi, [r9+r8*8+10h]
0x18005b095  add     rsi, rdx
0x18005b098  lea     rax, [rdx+28h]
0x18005b09c  mov     [rcx+40h], rax
0x18005b0a0  mov     rcx, [rbp+5Fh]
0x18005b0a4  lea     rax, aUnableToEnsure_21; "Unable to ensure RDPCTRL_SRC_CREATE_FRA"...
0x18005b0ab  mov     [rsp+110h+var_E8], rax
0x18005b0b0  mov     [rsp+110h+var_F0], rsi
0x18005b0b5  mov     r9d, 8007000Eh
0x18005b0bb  lea     r8, aOnecoreuapTerm_13; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18005b0c2  mov     edx, 1ACh
0x18005b0c7  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18005b0cc  mov     dword ptr [rsi+8], 1
0x18005b0d3  mov     dword ptr [rsi], 28h ; '('
0x18005b0d9  movups  xmm0, xmmword ptr [r12]
0x18005b0de  movdqu  xmmword ptr [rsi+0Ch], xmm0
0x18005b0e3  mov     [rsi+1Ch], r15
0x18005b0e7  mov     [rsi+24h], r14d
0x18005b0eb  mov     rcx, [rdi+150h]; this
0x18005b0f2  call    ?Flush@CFcWireEncoder@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::CFcWireEncoder::Flush(uint)
0x18005b0f7  nop
0x18005b0f8  sub     dword ptr [rbx+4Ch], 1
0x18005b0fc  jnz     short loc_18005B10F
0x18005b0fe  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x18005b105  lea     rcx, [rbx+10h]; SRWLock
0x18005b109  call    cs:__imp_ReleaseSRWLockExclusive
0x18005b10f  mov     rcx, [rbp+57h+var_30]
0x18005b113  xor     rcx, rsp; StackCookie
0x18005b116  call    __security_check_cookie
0x18005b11b  lea     r11, [rsp+110h+var_20]
0x18005b123  mov     rbx, [r11+38h]
0x18005b127  mov     rsi, [r11+40h]
0x18005b12b  mov     rsp, r11
0x18005b12e  pop     r15
0x18005b130  pop     r14
0x18005b132  pop     r12
0x18005b134  pop     rdi
0x18005b135  pop     rbp
0x18005b136  retn
0x18005b137  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18005b13e  mov     ecx, 6; int
0x18005b143  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005b149  mov     ecx, 5; int
0x18005b14e  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
