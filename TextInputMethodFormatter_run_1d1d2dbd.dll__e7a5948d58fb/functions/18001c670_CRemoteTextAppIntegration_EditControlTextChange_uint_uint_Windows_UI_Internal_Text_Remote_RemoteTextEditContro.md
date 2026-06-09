# CRemoteTextAppIntegration::EditControlTextChange(uint,uint,Windows::UI::Internal::Text::Remote::RemoteTextEditControlRange,Windows::UI::Internal::Text::Remote::RemoteTextEditControlRange,uint,int,Windows::UI::Internal::Text::Remote::RemoteTextKeyEventHostInfo,int,int,int,HSTRING__ *,int,HSTRING__ *,uint,uchar const *)

- ea: `0x18001c670`
- end: `0x18001c8ff`
- name: `?EditControlTextChange@CRemoteTextAppIntegration@@UEAAJIIURemoteTextEditControlRange@Remote@Text@Internal@UI@Windows@@0IHURemoteTextKeyEventHostInfo@34567@HHHPEAUHSTRING__@@H2IPEBE@Z`
- size: `655`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180006a14`
- `0x18001b7bc`
- `0x18001c670`
- `0x18002b610`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c715`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c72e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c715`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c72e`
- `CoreMessaging!MsgBlobCreateShared` at `0x18001c764`
- `CoreMessaging!MsgBlobCreateShared` at `0x18001c764`
- `CoreMessaging!MsgRelease` at `0x18001c8d0`
- `CoreMessaging!MsgRelease` at `0x18001c8d0`

## pseudocode

```c
__int64 __fastcall CRemoteTextAppIntegration::EditControlTextChange(
        __int64 a1,
        unsigned int a2,
        struct tagMsgRoutingInfo *a3,
        unsigned __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 a8,
        int a9,
        int a10,
        int a11,
        HSTRING string,
        int a13,
        HSTRING a14,
        unsigned int a15,
        __int64 a16)
{
  int v16; // ebx
  RemoteAppIntegrationServer *v18; // rcx
  unsigned int v19; // ebx
  PCWSTR StringRawBuffer; // rax
  _WORD *v21; // rsi
  PCWSTR v22; // rdi
  __int128 *v23; // rax
  __int128 v24; // xmm6
  __int128 v25; // xmm7
  __int128 v26; // xmm8
  int v27; // eax
  unsigned int v28; // r14d
  __int64 v30; // r10
  __int64 (__fastcall *v31)(__int64, __int64 *, _QWORD, _DWORD *, unsigned __int64, int, unsigned __int64, int, int, bool, _OWORD *, bool, __int64); // r12
  PCWSTR v32; // rcx
  int v33; // eax
  unsigned __int64 v34; // r8
  _WORD *v35; // rcx
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  UINT32 length; // [rsp+70h] [rbp-90h] BYREF
  UINT32 v42; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v43; // [rsp+78h] [rbp-88h]
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+90h] [rbp-70h] BYREF
  int v46; // [rsp+98h] [rbp-68h]
  _DWORD v47[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v48; // [rsp+ACh] [rbp-54h]
  unsigned __int64 v49; // [rsp+C0h] [rbp-40h]
  unsigned int v50; // [rsp+C8h] [rbp-38h] BYREF
  PCWSTR v51; // [rsp+D0h] [rbp-30h]
  unsigned int v52; // [rsp+D8h] [rbp-28h] BYREF
  _WORD *v53; // [rsp+E0h] [rbp-20h]
  _OWORD v54[6]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v16 = a4;
  v18 = *(RemoteAppIntegrationServer **)(a1 + 112);
  v49 = HIDWORD(a4);
  v43 = (unsigned int)a3;
  v45 = 0;
  v46 = 0;
  if ( RemoteAppIntegrationServer::RemoteToLocalClient(v18, a2, a3, (struct MessageObjectID *)&v45) )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v42 = 0;
    v21 = StringRawBuffer;
    v22 = WindowsGetStringRawBuffer(a14, &v42);
    v23 = (__int128 *)ConvertRemoteHostInfoHelper(v54, a8);
    v24 = *v23;
    v25 = v23[1];
    v26 = v23[2];
    v44 = 0;
    v27 = MsgBlobCreateShared(a16, a15, &v44);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x475,
        (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
        (const char *)(unsigned int)v27,
        v40);
      return v28;
    }
    v30 = *(_QWORD *)(a1 + 112);
    v31 = *(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, _DWORD *, unsigned __int64, int, unsigned __int64, int, int, bool, _OWORD *, bool, __int64))(*(_QWORD *)v30 + 144LL);
    if ( v22 )
    {
      v32 = v22;
      v33 = 0;
      v51 = v22;
      while ( *v22 )
      {
        ++v22;
        ++v33;
      }
      v50 = v33 | 0x80000000;
    }
    else
    {
      v32 = 0;
      v51 = 0;
    }
    v34 = (unsigned __int64)&v50 & -(__int64)(v32 != 0);
    if ( v21 )
    {
      v35 = v21;
      v36 = 0;
      v53 = v21;
      while ( *v21 )
      {
        ++v21;
        ++v36;
      }
      v52 = v36 | 0x80000000;
    }
    else
    {
      v35 = 0;
      v53 = 0;
    }
    v47[0] = a6;
    v48 = a5;
    v47[2] = v49;
    v54[0] = v24;
    v54[1] = v25;
    v54[2] = v26;
    v47[1] = v16;
    v19 = v31(
            v30,
            &v45,
            v43,
            v47,
            (unsigned __int64)&v52 & -(__int64)(v35 != 0),
            a11,
            v34,
            a13,
            a7,
            a9 != 0,
            v54,
            a10 != 0,
            v44);
    MsgRelease(v44, v37, v38, v39);
  }
  else
  {
    v19 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45E,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      (const char *)0x80070057LL,
      v40);
  }
  return v19;
}

```

## disassembly

```asm
0x18001c670  mov     rax, rsp
0x18001c673  push    rbp
0x18001c674  push    rbx
0x18001c675  push    rsi
0x18001c676  push    rdi
0x18001c677  push    r12
0x18001c679  push    r13
0x18001c67b  push    r14
0x18001c67d  push    r15
0x18001c67f  lea     rbp, [rsp-58h]
0x18001c684  sub     rsp, 158h
0x18001c68b  mov     r14, [rbp+90h+arg_38]
0x18001c692  mov     rbx, r9
0x18001c695  mov     rdi, [rbp+90h+string]
0x18001c69c  mov     r15, rcx
0x18001c69f  mov     rcx, [rcx+70h]; this
0x18001c6a3  xor     esi, esi
0x18001c6a5  mov     r12, [rbp+90h+arg_68]
0x18001c6ac  mov     r13, [rbp+90h+arg_78]
0x18001c6b3  movaps  xmmword ptr [rax-58h], xmm6
0x18001c6b7  movaps  xmmword ptr [rax-68h], xmm7
0x18001c6bb  movaps  xmmword ptr [rax-78h], xmm8
0x18001c6c0  mov     rax, r9
0x18001c6c3  shr     rax, 20h
0x18001c6c7  lea     r9, [rbp+90h+var_100]; struct MessageObjectID *
0x18001c6cb  mov     [rbp+90h+var_D0], rax
0x18001c6cf  mov     [rsp+190h+var_118], r8d
0x18001c6d4  mov     qword ptr [rbp+90h+var_100], rsi
0x18001c6d8  mov     dword ptr [rbp+90h+var_100+8], esi
0x18001c6db  call    ?RemoteToLocalClient@RemoteAppIntegrationServer@@QEAA_NIPEAUtagMsgRoutingInfo@@PEAUMessageObjectID@@@Z; RemoteAppIntegrationServer::RemoteToLocalClient(uint,tagMsgRoutingInfo *,MessageObjectID *)
0x18001c6e0  test    al, al
0x18001c6e2  jnz     short loc_18001C709
0x18001c6e4  mov     rcx, [rbp+98h]; this
0x18001c6eb  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\virtualization"...
0x18001c6f2  mov     ebx, 80070057h
0x18001c6f7  mov     edx, 45Eh; void *
0x18001c6fc  mov     r9d, ebx; char *
0x18001c6ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c704  jmp     loc_18001C8D6
0x18001c709  lea     rdx, [rsp+190h+length]; length
0x18001c70e  mov     [rsp+190h+length], esi
0x18001c712  mov     rcx, rdi; string
0x18001c715  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c71b  lea     rdx, [rsp+190h+var_11C]; length
0x18001c720  mov     [rsp+190h+var_11C], 0
0x18001c728  mov     rcx, r12; string
0x18001c72b  mov     rsi, rax
0x18001c72e  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c734  mov     rdx, r14
0x18001c737  lea     rcx, [rbp+90h+var_A0]
0x18001c73b  mov     rdi, rax
0x18001c73e  call    ?ConvertRemoteHostInfoHelper@@YA?AUKeyEventHostInfo@@AEBURemoteTextKeyEventHostInfo@Remote@Text@Internal@UI@Windows@@@Z; ConvertRemoteHostInfoHelper(Windows::UI::Internal::Text::Remote::RemoteTextKeyEventHostInfo const &)
0x18001c743  mov     edx, [rbp+90h+arg_70]
0x18001c749  lea     r8, [rbp+90h+var_110]
0x18001c74d  mov     rcx, r13
0x18001c750  movups  xmm6, xmmword ptr [rax]
0x18001c753  movups  xmm7, xmmword ptr [rax+10h]
0x18001c757  movups  xmm8, xmmword ptr [rax+20h]
0x18001c75c  mov     [rbp+90h+var_110], 0
0x18001c764  call    cs:__imp_MsgBlobCreateShared
0x18001c76a  xor     r13d, r13d
0x18001c76d  mov     r14d, eax
0x18001c770  test    eax, eax
0x18001c772  jns     short loc_18001C797
0x18001c774  mov     rcx, [rbp+98h]; this
0x18001c77b  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\virtualization"...
0x18001c782  mov     r9d, eax; char *
0x18001c785  mov     edx, 475h; void *
0x18001c78a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c78f  mov     eax, r14d
0x18001c792  jmp     loc_18001C8D8
0x18001c797  cmp     [rbp+90h+arg_48], r13d
0x18001c79e  mov     r10, [r15+70h]
0x18001c7a2  mov     edx, dword ptr [rbp+90h+arg_20]
0x18001c7a8  setnz   r14b
0x18001c7ac  cmp     [rbp+90h+arg_40], r13d
0x18001c7b3  mov     r9d, dword ptr [rbp+90h+arg_20+4]
0x18001c7ba  mov     rax, [r10]
0x18001c7bd  setnz   r15b
0x18001c7c1  mov     r11, [rbp+90h+var_110]
0x18001c7c5  mov     r12, [rax+90h]
0x18001c7cc  test    rdi, rdi
0x18001c7cf  jz      short loc_18001C7F3
0x18001c7d1  mov     rcx, rdi
0x18001c7d4  mov     rax, r13
0x18001c7d7  mov     [rbp+90h+var_C0], rcx
0x18001c7db  jmp     short loc_18001C7E4
0x18001c7dd  lea     rdi, [rdi+2]
0x18001c7e1  inc     rax
0x18001c7e4  cmp     [rdi], r13w
0x18001c7e8  jnz     short loc_18001C7DD
0x18001c7ea  bts     eax, 1Fh
0x18001c7ee  mov     [rbp+90h+var_C8], eax
0x18001c7f1  jmp     short loc_18001C7FA
0x18001c7f3  mov     rcx, r13
0x18001c7f6  mov     [rbp+90h+var_C0], rcx
0x18001c7fa  neg     rcx
0x18001c7fd  lea     rax, [rbp+90h+var_C8]
0x18001c801  sbb     r8, r8
0x18001c804  and     r8, rax
0x18001c807  test    rsi, rsi
0x18001c80a  jz      short loc_18001C82E
0x18001c80c  mov     rcx, rsi
0x18001c80f  mov     rax, r13
0x18001c812  mov     [rbp+90h+var_B0], rcx
0x18001c816  jmp     short loc_18001C81F
0x18001c818  lea     rsi, [rsi+2]
0x18001c81c  inc     rax
0x18001c81f  cmp     [rsi], r13w
0x18001c823  jnz     short loc_18001C818
0x18001c825  bts     eax, 1Fh
0x18001c829  mov     [rbp+90h+var_B8], eax
0x18001c82c  jmp     short loc_18001C835
0x18001c82e  mov     rcx, r13
0x18001c831  mov     [rbp+90h+var_B0], rcx
0x18001c835  mov     eax, [rbp+90h+arg_28]
0x18001c83b  neg     rcx
0x18001c83e  movaps  xmm0, [rbp+90h+var_100]
0x18001c842  mov     rcx, r10
0x18001c845  mov     [rsp+190h+var_130], r11
0x18001c84a  mov     [rsp+190h+var_138], r14b
0x18001c84f  mov     [rbp+90h+var_F0], eax
0x18001c852  mov     rax, [rbp+90h+var_D0]
0x18001c856  mov     [rbp+90h+var_E4], edx
0x18001c859  mov     edx, [rbp+90h+arg_30]
0x18001c85f  mov     [rbp+90h+var_E8], eax
0x18001c862  lea     rax, [rbp+90h+var_B8]
0x18001c866  mov     [rbp+90h+var_E0], r9d
0x18001c86a  sbb     r9, r9
0x18001c86d  and     r9, rax
0x18001c870  movaps  [rbp+90h+var_A0], xmm6
0x18001c874  lea     rax, [rbp+90h+var_A0]
0x18001c878  movaps  [rbp+90h+var_90], xmm7
0x18001c87c  mov     [rsp+190h+var_140], rax
0x18001c881  mov     rax, r12
0x18001c884  mov     [rsp+190h+var_148], r15b
0x18001c889  mov     [rsp+190h+var_150], edx
0x18001c88d  mov     edx, [rbp+90h+arg_60]
0x18001c893  mov     [rsp+190h+var_158], edx
0x18001c897  mov     edx, [rbp+90h+arg_50]
0x18001c89d  mov     [rsp+190h+var_160], r8
0x18001c8a2  mov     r8d, [rsp+190h+var_118]
0x18001c8a7  mov     [rsp+190h+var_168], edx
0x18001c8ab  lea     rdx, [rbp+90h+var_100]
0x18001c8af  mov     [rsp+190h+var_170], r9
0x18001c8b4  lea     r9, [rbp+90h+var_F0]
0x18001c8b8  movaps  [rbp+90h+var_80], xmm8
0x18001c8bd  mov     [rbp+90h+var_EC], ebx
0x18001c8c0  movdqa  [rbp+90h+var_100], xmm0
0x18001c8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8ca  mov     rcx, [rbp+90h+var_110]
0x18001c8ce  mov     ebx, eax
0x18001c8d0  call    cs:__imp_MsgRelease
0x18001c8d6  mov     eax, ebx
0x18001c8d8  lea     r11, [rsp+190h+var_38]
0x18001c8e0  movaps  xmm6, xmmword ptr [r11-18h]
0x18001c8e5  movaps  xmm7, xmmword ptr [r11-28h]
0x18001c8ea  movaps  xmm8, xmmword ptr [r11-38h]
0x18001c8ef  mov     rsp, r11
0x18001c8f2  pop     r15
0x18001c8f4  pop     r14
0x18001c8f6  pop     r13
0x18001c8f8  pop     r12
0x18001c8fa  pop     rdi
0x18001c8fb  pop     rsi
0x18001c8fc  pop     rbx
0x18001c8fd  pop     rbp
0x18001c8fe  retn
```
