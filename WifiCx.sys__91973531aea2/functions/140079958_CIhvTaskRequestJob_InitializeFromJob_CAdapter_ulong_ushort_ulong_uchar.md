# CIhvTaskRequestJob::InitializeFromJob(CAdapter *,ulong,ushort,ulong,uchar *)

- ea: `0x140079958`
- end: `0x140079f37`
- name: `?InitializeFromJob@CIhvTaskRequestJob@@QEAAHPEAVCAdapter@@KGKPEAE@Z`
- size: `1503`
- prototype: `__int64 __fastcall(CIhvTaskRequestJob *__hidden this, struct CAdapter *, unsigned int, unsigned __int16, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, service_task`

## callers

- `0x140026010`
- `0x140055628`

## callees

- `0x14000c778`
- `0x140014b30`
- `0x14001d860`
- `0x14001de20`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x14003fd10`
- `0x140040804`
- `0x1400413ec`
- `0x14004a4fc`
- `0x14005f8bc`
- `0x140079958`

## pseudocode

```c
__int64 __fastcall CIhvTaskRequestJob::InitializeFromJob(
        CIhvTaskRequestJob *this,
        struct CAdapter *a2,
        int a3,
        __int16 a4,
        unsigned int a5,
        unsigned __int8 *a6)
{
  __int64 *v10; // rdx
  __int64 v11; // rcx
  int v12; // edx
  unsigned int WdiTaskIhvToIhv; // ebx
  int v14; // r8d
  char v15; // cl
  int v16; // edx
  struct _OID_HANDLER_ENTRY *v17; // rax
  int v18; // edx
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  struct _OID_HANDLER_ENTRY *v22; // rax
  struct _OID_HANDLER_ENTRY *OidHandlerEntry; // rax
  int v24; // r8d
  const char *v25; // rdx
  const char *v26; // rcx
  int v27; // r8d
  const char *v28; // rdx
  const char *v29; // rbx
  const char *v30; // rax
  int v31; // edx
  int v32; // r8d
  __int64 v33; // rdx
  unsigned int v34; // eax
  int v35; // edx
  int v36; // r8d
  int v37; // r9d
  int v38; // ebx
  __int64 v39; // rdi
  int v40; // r8d
  int v41; // edx
  int v42; // r8d
  __int64 v44; // [rsp+28h] [rbp-91h]
  __int64 v45; // [rsp+38h] [rbp-81h]
  int v46; // [rsp+80h] [rbp-39h] BYREF
  int v47; // [rsp+88h] [rbp-31h] BYREF
  __int64 v48; // [rsp+90h] [rbp-29h]
  char v49; // [rsp+98h] [rbp-21h]
  __int64 v50; // [rsp+A0h] [rbp-19h] BYREF
  int v51; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-9h]
  char v53; // [rsp+B8h] [rbp-1h]

  v51 = 0;
  v50 = (unsigned int)v50 & 0xFFFFFFFE;
  v46 &= ~1u;
  v52 = HIDWORD(v50);
  v53 = BYTE4(v50);
  v47 = HIDWORD(v50);
  v48 = HIDWORD(v50);
  v49 = BYTE4(v50);
  v10 = WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v10,
      a3,
      202,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  *((_QWORD *)this + 67) = a2;
  v11 = *((_QWORD *)this + 131);
  *((_DWORD *)this + 14) = a3;
  *((_WORD *)this + 272) = a4;
  if ( v11 )
  {
    FreeGenerated(v11, v10);
    *((_QWORD *)this + 131) = 0;
  }
  WdiTaskIhvToIhv = ParseWdiIndicationIhvTaskRequestFromIhv(a5, a6, (char *)a2 + 5384, &v50);
  if ( WdiTaskIhvToIhv )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v44) = WdiTaskIhvToIhv;
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        1,
        203,
        (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
        v44);
    }
    goto LABEL_50;
  }
  v15 = BYTE4(v50);
  *((_DWORD *)this + 137) = HIDWORD(v50);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 4;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v14,
      204,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v15,
      a4);
  }
  *((_DWORD *)this + 139) = a4 == -1;
  v16 = *((_DWORD *)this + 137);
  if ( v16 == 1 )
  {
    OidHandlerEntry = COidJobBase::s_FindOidHandlerEntry(0xD010310u);
    if ( !OidHandlerEntry )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v20 = 205;
        goto LABEL_29;
      }
      goto LABEL_30;
    }
    v21 = *((_DWORD *)OidHandlerEntry + 3);
    *((_WORD *)this + 276) = 256;
    goto LABEL_32;
  }
  if ( *((_DWORD *)this + 137) == 2 )
  {
    v22 = COidJobBase::s_FindOidHandlerEntry(0xE010181u);
    if ( !v22 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v20 = 206;
        goto LABEL_29;
      }
LABEL_30:
      WdiTaskIhvToIhv = -1073741637;
      goto LABEL_50;
    }
    v21 = *((_DWORD *)v22 + 3);
    *((_WORD *)this + 276) = 257;
LABEL_32:
    *((_DWORD *)this + 140) = v21;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v45) = v21;
      LOBYTE(v18) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        v19,
        209,
        (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v45);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v25 = "Port";
        v26 = "Adapter";
        if ( *((_DWORD *)this + 139) != 1 )
          v26 = "Port";
        LOBYTE(v25) = 4;
        WPP_RECORDER_SF_qDs(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v25,
          v24,
          210,
          (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
          (char)this,
          *((_DWORD *)this + 4),
          (__int64)v26);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v28 = "No";
          v29 = "Yes";
          v30 = "Yes";
          if ( !*((_BYTE *)this + 552) )
            v30 = "No";
          LOBYTE(v28) = 4;
          WPP_RECORDER_SF_qDs(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v28,
            v27,
            211,
            (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
            (char)this,
            *((_DWORD *)this + 4),
            (__int64)v30);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            if ( !*((_BYTE *)this + 553) )
              v29 = "No";
            LOBYTE(v31) = 4;
            WPP_RECORDER_SF_qDs(
              WPP_GLOBAL_Control->DeviceExtension,
              v31,
              v32,
              212,
              (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
              (char)this,
              *((_DWORD *)this + 4),
              (__int64)v29);
          }
        }
      }
    }
    v33 = *((_QWORD *)this + 67);
    v34 = CJobBase::Initialize(
            (__int64)this,
            v33 + 736,
            v33 + 1120,
            v33 + 928,
            v33 + 848,
            161,
            *((_BYTE *)this + 552),
            *((_BYTE *)this + 553),
            *((_DWORD *)this + 139),
            *((_DWORD *)this + 140),
            (v33 + 8) & -(__int64)(v33 != 0),
            (__int64)a2,
            a3,
            0);
    WdiTaskIhvToIhv = v34;
    if ( v34 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_50;
      v37 = 213;
      LODWORD(v45) = v34;
    }
    else
    {
      v38 = v51;
      v39 = v52;
      v46 = v50 & 1 | v46 & 0xFFFFFFFE;
      ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(&v47);
      v40 = *((_QWORD *)this + 67) + 5384;
      v49 = 0;
      v47 = v38;
      v48 = v39;
      WdiTaskIhvToIhv = GenerateWdiTaskIhvToIhv((unsigned int)&v46, 48, v40, (int)this + 1040, (__int64)this + 1048);
      if ( !WdiTaskIhvToIhv || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_50;
      v37 = 214;
      LODWORD(v45) = WdiTaskIhvToIhv;
    }
    LOBYTE(v35) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v35,
      v36,
      v37,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v45);
    goto LABEL_50;
  }
  if ( *((_DWORD *)this + 137) == 3 )
  {
    v17 = COidJobBase::s_FindOidHandlerEntry(0xE020183u);
    if ( !v17 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v20 = 207;
LABEL_29:
        LOBYTE(v18) = 2;
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v18,
          v19,
          v20,
          (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
          (char)this,
          *((_DWORD *)this + 4));
        goto LABEL_30;
      }
      goto LABEL_30;
    }
    v21 = *((_DWORD *)v17 + 3);
    *((_WORD *)this + 276) = 1;
    goto LABEL_32;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v44) = *((_DWORD *)this + 137);
    LOBYTE(v16) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      1,
      208,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      v44);
  }
  WdiTaskIhvToIhv = -1073676267;
LABEL_50:
  CleanupParsedWdiIndicationIhvTaskRequestFromIhv(&v50);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v41) = 5;
    LODWORD(v45) = WdiTaskIhvToIhv;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v41,
      v42,
      215,
      (__int64)WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v45);
  }
  ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(&v47);
  ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(&v51);
  return WdiTaskIhvToIhv;
}

```

## disassembly

```asm
0x140079958  push    rbp
0x14007995a  push    rbx
0x14007995b  push    rsi
0x14007995c  push    rdi
0x14007995d  push    r12
0x14007995f  push    r13
0x140079961  push    r14
0x140079963  push    r15
0x140079965  lea     rbp, [rsp-0Fh]
0x14007996a  sub     rsp, 0C8h
0x140079971  xor     r13d, r13d
0x140079974  movzx   edi, r9w
0x140079978  mov     eax, 0FFFFFFFEh
0x14007997d  mov     [rbp+47h+var_5C], r13
0x140079981  and     [rbp+47h+var_60], eax
0x140079984  mov     r12d, r8d
0x140079987  and     [rbp+47h+var_80], eax
0x14007998a  mov     r15, rdx
0x14007998d  mov     rsi, rcx
0x140079990  mov     [rbp+47h+var_50], r13
0x140079994  mov     [rbp+47h+var_48], r13b
0x140079998  mov     [rbp+47h+var_78], r13d
0x14007999c  mov     [rbp+47h+var_70], r13
0x1400799a0  mov     [rbp+47h+var_68], r13b
0x1400799a4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400799ab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400799b2  lea     rdx, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x1400799b9  jz      short loc_1400799F1
0x1400799bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400799c2  cmp     byte ptr [rcx+29h], 5
0x1400799c6  jnb     short loc_1400799CF
0x1400799c8  cmp     [rcx+48h], r13w
0x1400799cd  jz      short loc_1400799F1
0x1400799cf  mov     eax, [rsi+10h]
0x1400799d2  mov     r9d, 0CAh
0x1400799d8  mov     rcx, [rcx+40h]
0x1400799dc  mov     [rsp+100h+var_D0], eax
0x1400799e0  mov     [rsp+100h+var_D8], rsi
0x1400799e5  mov     [rsp+100h+var_E0], rdx
0x1400799ea  mov     dl, 5
0x1400799ec  call    WPP_RECORDER_SF_qD
0x1400799f1  lea     r14, [rsi+418h]
0x1400799f8  mov     [rsi+218h], r15
0x1400799ff  mov     rcx, [r14]
0x140079a02  mov     [rsi+38h], r12d
0x140079a06  mov     [rsi+220h], di
0x140079a0d  test    rcx, rcx
0x140079a10  jz      short loc_140079A1A
0x140079a12  call    FreeGenerated
0x140079a17  mov     [r14], r13
0x140079a1a  mov     rdx, [rbp+47h+arg_28]
0x140079a1e  lea     r8, [r15+1508h]
0x140079a25  mov     ecx, [rbp+47h+arg_20]
0x140079a28  lea     r9, [rbp+47h+var_60]
0x140079a2c  call    ParseWdiIndicationIhvTaskRequestFromIhv
0x140079a31  mov     ebx, eax
0x140079a33  test    eax, eax
0x140079a35  jz      short loc_140079A7E
0x140079a37  lea     rax, WPP_RECORDER_INITIALIZED
0x140079a3e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140079a45  lea     rdi, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079a4c  jz      loc_140079EBB
0x140079a52  mov     rcx, cs:WPP_GLOBAL_Control
0x140079a59  mov     r9d, 0CBh
0x140079a5f  mov     dword ptr [rsp+100h+var_D8], ebx
0x140079a63  mov     r8d, 1
0x140079a69  mov     dl, 2
0x140079a6b  mov     [rsp+100h+var_E0], rdi
0x140079a70  mov     rcx, [rcx+40h]
0x140079a74  call    WPP_RECORDER_SF_d
0x140079a79  jmp     loc_140079EBB
0x140079a7e  mov     ecx, dword ptr [rbp+47h+var_5C]
0x140079a81  mov     [rsi+224h], ecx
0x140079a87  lea     rbx, WPP_RECORDER_INITIALIZED
0x140079a8e  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140079a95  jz      short loc_140079ACF
0x140079a97  mov     eax, [rsi+10h]
0x140079a9a  mov     r9d, 0CCh
0x140079aa0  mov     [rsp+100h+var_C0], edi
0x140079aa4  mov     dl, 4
0x140079aa6  mov     dword ptr [rsp+100h+var_C8], ecx
0x140079aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x140079ab1  mov     [rsp+100h+var_D0], eax
0x140079ab5  lea     rax, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079abc  mov     [rsp+100h+var_D8], rsi
0x140079ac1  mov     [rsp+100h+var_E0], rax
0x140079ac6  mov     rcx, [rcx+40h]
0x140079aca  call    WPP_RECORDER_SF_qDdd
0x140079acf  mov     ecx, 0FFFFh
0x140079ad4  mov     eax, r13d
0x140079ad7  cmp     di, cx
0x140079ada  setz    al
0x140079add  mov     [rsi+22Ch], eax
0x140079ae3  mov     edx, [rsi+224h]
0x140079ae9  mov     ecx, edx
0x140079aeb  sub     ecx, 1
0x140079aee  jz      loc_140079BB4
0x140079af4  sub     ecx, 1
0x140079af7  jz      loc_140079B7F
0x140079afd  cmp     ecx, 1
0x140079b00  jz      short loc_140079B43
0x140079b02  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140079b09  lea     rdi, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079b10  jz      short loc_140079B39
0x140079b12  mov     rcx, cs:WPP_GLOBAL_Control
0x140079b19  mov     r9d, 0D0h
0x140079b1f  mov     dword ptr [rsp+100h+var_D8], edx
0x140079b23  mov     r8d, 1
0x140079b29  mov     dl, 2
0x140079b2b  mov     [rsp+100h+var_E0], rdi
0x140079b30  mov     rcx, [rcx+40h]
0x140079b34  call    WPP_RECORDER_SF_d
0x140079b39  mov     ebx, 0C0010015h
0x140079b3e  jmp     loc_140079EBB
0x140079b43  mov     ecx, 0E020183h; unsigned int
0x140079b48  call    ?s_FindOidHandlerEntry@COidJobBase@@SAPEAU_OID_HANDLER_ENTRY@@K@Z; COidJobBase::s_FindOidHandlerEntry(ulong)
0x140079b4d  test    rax, rax
0x140079b50  jnz     short loc_140079B6E
0x140079b52  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140079b59  lea     rdi, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079b60  jz      loc_140079BFC
0x140079b66  mov     r9d, 0CFh
0x140079b6c  jmp     short loc_140079BD9
0x140079b6e  mov     eax, [rax+0Ch]
0x140079b71  mov     word ptr [rsi+228h], 1
0x140079b7a  jmp     loc_140079C12
0x140079b7f  mov     ecx, 0E010181h; unsigned int
0x140079b84  call    ?s_FindOidHandlerEntry@COidJobBase@@SAPEAU_OID_HANDLER_ENTRY@@K@Z; COidJobBase::s_FindOidHandlerEntry(ulong)
0x140079b89  test    rax, rax
0x140079b8c  jnz     short loc_140079BA6
0x140079b8e  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140079b95  lea     rdi, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079b9c  jz      short loc_140079BFC
0x140079b9e  mov     r9d, 0CEh
0x140079ba4  jmp     short loc_140079BD9
0x140079ba6  mov     eax, [rax+0Ch]
0x140079ba9  mov     word ptr [rsi+228h], 101h
0x140079bb2  jmp     short loc_140079C12
0x140079bb4  mov     ecx, 0D010310h; unsigned int
0x140079bb9  call    ?s_FindOidHandlerEntry@COidJobBase@@SAPEAU_OID_HANDLER_ENTRY@@K@Z; COidJobBase::s_FindOidHandlerEntry(ulong)
0x140079bbe  test    rax, rax
0x140079bc1  jnz     short loc_140079C06
0x140079bc3  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140079bca  lea     rdi, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079bd1  jz      short loc_140079BFC
0x140079bd3  mov     r9d, 0CDh
0x140079bd9  mov     rcx, cs:WPP_GLOBAL_Control
0x140079be0  mov     dl, 2
0x140079be2  mov     eax, [rsi+10h]
0x140079be5  mov     [rsp+100h+var_D0], eax
0x140079be9  mov     [rsp+100h+var_D8], rsi
0x140079bee  mov     rcx, [rcx+40h]
0x140079bf2  mov     [rsp+100h+var_E0], rdi
0x140079bf7  call    WPP_RECORDER_SF_qD
0x140079bfc  mov     ebx, 0C00000BBh
0x140079c01  jmp     loc_140079EBB
0x140079c06  mov     eax, [rax+0Ch]
0x140079c09  mov     word ptr [rsi+228h], 100h
0x140079c12  mov     [rsi+230h], eax
0x140079c18  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140079c1f  jz      loc_140079D5D
0x140079c25  mov     rcx, cs:WPP_GLOBAL_Control
0x140079c2c  lea     rdi, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079c33  mov     dword ptr [rsp+100h+var_C8], eax
0x140079c37  mov     r9d, 0D1h
0x140079c3d  mov     eax, [rsi+10h]
0x140079c40  mov     dl, 4
0x140079c42  mov     [rsp+100h+var_D0], eax
0x140079c46  mov     rcx, [rcx+40h]
0x140079c4a  mov     [rsp+100h+var_D8], rsi
0x140079c4f  mov     [rsp+100h+var_E0], rdi
0x140079c54  call    WPP_RECORDER_SF_qDD
0x140079c59  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140079c60  jz      loc_140079D5D
0x140079c66  cmp     dword ptr [rsi+22Ch], 1
0x140079c6d  lea     rdx, aPort; "Port"
0x140079c74  mov     eax, [rsi+10h]
0x140079c77  lea     rcx, aAdapter; "Adapter"
0x140079c7e  cmovnz  rcx, rdx
0x140079c82  mov     r9d, 0D2h
0x140079c88  mov     [rsp+100h+var_C8], rcx
0x140079c8d  mov     dl, 4
0x140079c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140079c96  mov     [rsp+100h+var_D0], eax
0x140079c9a  mov     [rsp+100h+var_D8], rsi
0x140079c9f  mov     [rsp+100h+var_E0], rdi
0x140079ca4  mov     rcx, [rcx+40h]
0x140079ca8  call    WPP_RECORDER_SF_qDs
0x140079cad  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x140079cb4  jz      loc_140079D5D
0x140079cba  cmp     [rsi+228h], r13b
0x140079cc1  lea     rdx, aNo; "No"
0x140079cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140079ccf  lea     rbx, aYes; "Yes"
0x140079cd6  mov     rax, rbx
0x140079cd9  mov     r9d, 0D3h
0x140079cdf  cmovz   rax, rdx
0x140079ce3  mov     dl, 4
0x140079ce5  mov     [rsp+100h+var_C8], rax
0x140079cea  mov     eax, [rsi+10h]
0x140079ced  mov     rcx, [rcx+40h]
0x140079cf1  mov     [rsp+100h+var_D0], eax
0x140079cf5  mov     [rsp+100h+var_D8], rsi
0x140079cfa  mov     [rsp+100h+var_E0], rdi
0x140079cff  call    WPP_RECORDER_SF_qDs
0x140079d04  lea     rdi, WPP_RECORDER_INITIALIZED
0x140079d0b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140079d12  jz      short loc_140079D64
0x140079d14  cmp     [rsi+229h], r13b
0x140079d1b  lea     rax, aNo; "No"
0x140079d22  mov     rcx, cs:WPP_GLOBAL_Control
0x140079d29  mov     r9d, 0D4h
0x140079d2f  cmovz   rbx, rax
0x140079d33  mov     dl, 4
0x140079d35  mov     eax, [rsi+10h]
0x140079d38  mov     [rsp+100h+var_C8], rbx
0x140079d3d  mov     rcx, [rcx+40h]
0x140079d41  mov     [rsp+100h+var_D0], eax
0x140079d45  lea     rax, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079d4c  mov     [rsp+100h+var_D8], rsi
0x140079d51  mov     [rsp+100h+var_E0], rax
0x140079d56  call    WPP_RECORDER_SF_qDs
0x140079d5b  jmp     short loc_140079D64
0x140079d5d  lea     rdi, WPP_RECORDER_INITIALIZED
0x140079d64  mov     rdx, [rsi+218h]
0x140079d6b  mov     [rsp+100h+var_98], r13b
0x140079d70  mov     rax, rdx
0x140079d73  mov     [rsp+100h+var_A0], r12d
0x140079d78  neg     rax
0x140079d7b  mov     eax, [rsi+230h]
0x140079d81  mov     [rsp+100h+var_A8], r15
0x140079d86  lea     rcx, [rdx+8]
0x140079d8a  sbb     r10, r10
0x140079d8d  lea     r9, [rdx+3A0h]
0x140079d94  and     r10, rcx
0x140079d97  lea     r8, [rdx+460h]
0x140079d9e  mov     [rsp+100h+var_B0], r10
0x140079da3  lea     rcx, [rdx+350h]
0x140079daa  mov     [rsp+100h+var_B8], eax
0x140079dae  add     rdx, 2E0h
0x140079db5  mov     eax, [rsi+22Ch]
0x140079dbb  mov     [rsp+100h+var_C0], eax
0x140079dbf  mov     al, [rsi+229h]
0x140079dc5  mov     byte ptr [rsp+100h+var_C8], al
0x140079dc9  mov     al, [rsi+228h]
0x140079dcf  mov     byte ptr [rsp+100h+var_D0], al
0x140079dd3  mov     dword ptr [rsp+100h+var_D8], 0A1h
0x140079ddb  mov     [rsp+100h+var_E0], rcx
0x140079de0  mov     rcx, rsi
0x140079de3  call    ?Initialize@CJobBase@@IEAAHPEAVEventQueue@@PEAVDeviceCommandScheduler@@PEAVActiveJobsList@@PEAVSerializedJobList@@W4_WFC_JOB_TYPE@@_N5W4_WFC_SERIALIZED_JOB_PRIORITY_SCOPE@@W4_WFC_SERIALIZED_JOB_PRIORITY@@PEAVIPropertyCacheDirectory@@PEAVINdisConversion@@K55@Z; CJobBase::Initialize(EventQueue *,DeviceCommandScheduler *,ActiveJobsList *,SerializedJobList *,_WFC_JOB_TYPE,bool,bool,_WFC_SERIALIZED_JOB_PRIORITY_SCOPE,_WFC_SERIALIZED_JOB_PRIORITY,IPropertyCacheDirectory *,INdisConversion *,ulong,bool,bool)
0x140079de8  mov     ebx, eax
0x140079dea  test    eax, eax
0x140079dec  jz      short loc_140079E34
0x140079dee  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140079df5  lea     rdi, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079dfc  jz      loc_140079EBB
0x140079e02  mov     r9d, 0D5h
0x140079e08  mov     dword ptr [rsp+100h+var_C8], eax
0x140079e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140079e13  mov     dl, 2
0x140079e15  mov     eax, [rsi+10h]
0x140079e18  mov     [rsp+100h+var_D0], eax
0x140079e1c  mov     [rsp+100h+var_D8], rsi
0x140079e21  mov     rcx, [rcx+40h]
0x140079e25  mov     [rsp+100h+var_E0], rdi
0x140079e2a  call    WPP_RECORDER_SF_qDD
0x140079e2f  jmp     loc_140079EBB
0x140079e34  mov     ecx, [rbp+47h+var_80]
0x140079e37  mov     eax, [rbp+47h+var_60]
0x140079e3a  and     ecx, 0FFFFFFFEh
0x140079e3d  mov     ebx, dword ptr [rbp+47h+var_5C+4]
0x140079e40  and     eax, 1
0x140079e43  mov     rdi, [rbp+47h+var_50]
0x140079e47  or      ecx, eax
0x140079e49  mov     [rbp+47h+var_80], ecx
0x140079e4c  lea     rcx, [rbp+47h+var_78]; void *
0x140079e50  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ; ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(void)
0x140079e55  mov     r8, [rsi+218h]
0x140079e5c  lea     r9, [rsi+410h]
0x140079e63  add     r8, 1508h
0x140079e6a  mov     [rbp+47h+var_68], r13b
0x140079e6e  mov     edx, 30h ; '0'
0x140079e73  mov     [rbp+47h+var_78], ebx
0x140079e76  lea     rcx, [rbp+47h+var_80]
0x140079e7a  mov     [rbp+47h+var_70], rdi
0x140079e7e  mov     [rsp+100h+var_E0], r14
0x140079e83  call    GenerateWdiTaskIhvToIhv
0x140079e88  mov     ebx, eax
0x140079e8a  test    eax, eax
0x140079e8c  jz      short loc_140079EB4
0x140079e8e  lea     rax, WPP_RECORDER_INITIALIZED
0x140079e95  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140079e9c  lea     rdi, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079ea3  jz      short loc_140079EBB
0x140079ea5  mov     r9d, 0D6h
0x140079eab  mov     dword ptr [rsp+100h+var_C8], ebx
0x140079eaf  jmp     loc_140079E0C
0x140079eb4  lea     rdi, WPP_2d39e0cebfc73daf8408a6f3c3e3de18_Traceguids
0x140079ebb  lea     rcx, [rbp+47h+var_60]
0x140079ebf  call    CleanupParsedWdiIndicationIhvTaskRequestFromIhv
  ... truncated ...
```
