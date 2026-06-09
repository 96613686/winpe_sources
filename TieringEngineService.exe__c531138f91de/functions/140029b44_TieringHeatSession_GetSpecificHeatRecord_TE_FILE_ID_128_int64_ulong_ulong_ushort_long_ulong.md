# TieringHeatSession::GetSpecificHeatRecord(TE_FILE_ID_128 *,__int64,ulong *,ulong *,ushort *,long *,ulong * *)

- ea: `0x140029b44`
- end: `0x140029de6`
- name: `?GetSpecificHeatRecord@TieringHeatSession@@QEAAJPEAUTE_FILE_ID_128@@_JPEAK2PEAGPEAJPEAPEAK@Z`
- size: `674`
- prototype: `__int64 __fastcall(TieringHeatSession *this, struct TE_FILE_ID_128 *pvData, __int64, unsigned int *, unsigned int *, unsigned __int16 *, int *, unsigned int **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x14003db78`

## callees

- `0x140004ef0`
- `0x140005420`
- `0x14001cd80`
- `0x140025dd0`
- `0x14002670c`
- `0x140028e7c`
- `0x140029b44`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140029bd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140029bd1`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::GetSpecificHeatRecord(
        TieringHeatSession *this,
        struct TE_FILE_ID_128 *pvData,
        __int64 a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned __int16 *a6,
        int *a7,
        unsigned int **a8)
{
  __int64 v11; // rcx
  char *v12; // rax
  unsigned int v13; // ebx
  char v14; // al
  unsigned int v15; // ecx
  __int64 v16; // rdx
  bool v17; // cf
  __int64 i; // rax
  unsigned __int8 v20; // [rsp+60h] [rbp-41h] BYREF
  char v21; // [rsp+61h] [rbp-40h] BYREF
  char v22[2]; // [rsp+62h] [rbp-3Fh] BYREF
  int v23; // [rsp+64h] [rbp-3Dh] BYREF
  unsigned int *v24; // [rsp+68h] [rbp-39h]
  int *v25; // [rsp+70h] [rbp-31h]
  _BYTE v26[8]; // [rsp+78h] [rbp-29h] BYREF
  int HeatRecord; // [rsp+80h] [rbp-21h]
  unsigned __int16 v28[4]; // [rsp+88h] [rbp-19h] BYREF
  int v29; // [rsp+90h] [rbp-11h]
  __int16 v30; // [rsp+94h] [rbp-Dh]

  v11 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v24 = a4;
  v25 = a7;
  *(_QWORD *)(v11 + 8) = "TieringHeatSession::GetSpecificHeatRecord";
  CHResultImp::CHResultImp((CHResultImp *)v26);
  v20 = 0;
  v21 = 0;
  v22[0] = 0;
  *a7 = 0;
  *(_QWORD *)v28 = 0;
  v29 = 0;
  v30 = 0;
  v12 = (char *)CoTaskMemAlloc(0x1Cu);
  *a8 = (unsigned int *)v12;
  if ( v12 )
  {
    *(_OWORD *)v12 = 0;
    *(_OWORD *)(v12 + 12) = 0;
    HeatRecord = TieringHeatSession::GetHeatRecord(
                   this,
                   pvData,
                   a3,
                   &v20,
                   (unsigned __int8 *)&v21,
                   (unsigned __int8 *)v22,
                   a6,
                   v28);
    v13 = HeatRecord;
    if ( HeatRecord >= 0 )
    {
      v23 = 0;
      TieringHeatSession::AddCurrentCountAndAgeHistory(this, pvData, a3, 0, v22[0], *a6, v21, v28, &v23, a5, 0);
      if ( (v21 & 8) != 0 )
      {
        v14 = 1;
      }
      else if ( (v21 & 4) != 0 )
      {
        v14 = 2;
      }
      else
      {
        v15 = *a5;
        v16 = **((_QWORD **)this + 5);
        if ( (v20 & 0x10) != 0 )
          v17 = v15 < *(_DWORD *)(v16 + 228);
        else
          v17 = v15 < *(_DWORD *)(v16 + 224);
        v14 = v17 + 1;
      }
      v20 |= v14;
      *v24 = v20 | (((unsigned __int8)v21 | ((unsigned __int8)v22[0] << 8)) << 8);
      *v25 = 7;
      for ( i = 0; i != 7; ++i )
        (*a8)[i] = v28[i];
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiDSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)pvData + 1),
        *(_QWORD *)pvData,
        a3,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        HeatRecord);
    }
  }
  else
  {
    v13 = -2147024882;
    HeatRecord = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        7,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        14);
    }
  }
  CHResultImp::~CHResultImp((CHResultImp *)v26);
  return v13;
}

```

## disassembly

```asm
0x140029b44  push    rbp
0x140029b46  push    rbx
0x140029b47  push    rsi
0x140029b48  push    rdi
0x140029b49  push    r12
0x140029b4b  push    r13
0x140029b4d  push    r14
0x140029b4f  push    r15
0x140029b51  lea     rbp, [rsp-7]
0x140029b56  sub     rsp, 0A8h
0x140029b5d  mov     rax, cs:__security_cookie
0x140029b64  xor     rax, rsp
0x140029b67  mov     [rbp+3Fh+var_48], rax
0x140029b6b  mov     rax, gs:58h
0x140029b74  mov     rdi, rcx
0x140029b77  mov     rbx, [rbp+3Fh+arg_30]
0x140029b7b  mov     rsi, rdx
0x140029b7e  mov     r15, [rbp+3Fh+arg_20]
0x140029b82  mov     r14, r8
0x140029b85  mov     r12, [rbp+3Fh+arg_28]
0x140029b89  mov     rcx, [rax]
0x140029b8c  lea     rax, aTieringheatses_7; "TieringHeatSession::GetSpecificHeatReco"...
0x140029b93  mov     r13, [rbp+3Fh+arg_38]
0x140029b9a  mov     edx, 8
0x140029b9f  mov     [rbp+3Fh+var_78], r9
0x140029ba3  mov     [rbp+3Fh+var_70], rbx
0x140029ba7  mov     [rdx+rcx], rax
0x140029bab  lea     rcx, [rbp+3Fh+var_68]; this
0x140029baf  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140029bb4  xor     ecx, ecx
0x140029bb6  xor     eax, eax
0x140029bb8  mov     [rbp+3Fh+var_80], cl
0x140029bbb  mov     [rbp+3Fh+var_7F], cl
0x140029bbe  mov     [rbp+3Fh+var_7E], cl
0x140029bc1  mov     [rbx], ecx
0x140029bc3  lea     ecx, [rax+1Ch]; cb
0x140029bc6  mov     qword ptr [rbp+3Fh+var_58], rax
0x140029bca  mov     [rbp+3Fh+var_50], eax
0x140029bcd  mov     [rbp+3Fh+var_4C], ax
0x140029bd1  call    cs:__imp_CoTaskMemAlloc
0x140029bd7  mov     [r13+0], rax
0x140029bdb  test    rax, rax
0x140029bde  jnz     short loc_140029C43
0x140029be0  mov     ebx, 8007000Eh
0x140029be5  mov     [rbp+3Fh+var_60], ebx
0x140029be8  mov     rcx, cs:WPP_GLOBAL_Control
0x140029bef  lea     rax, WPP_GLOBAL_Control
0x140029bf6  cmp     rcx, rax
0x140029bf9  jz      loc_140029DBB
0x140029bff  test    byte ptr [rcx+1Ch], 1
0x140029c03  jz      loc_140029DBB
0x140029c09  mov     al, 2
0x140029c0b  cmp     [rcx+19h], al
0x140029c0e  jb      loc_140029DBB
0x140029c14  mov     rax, [rdi+28h]
0x140029c18  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140029c1f  mov     rcx, [rcx+10h]
0x140029c23  mov     edx, 47h ; 'G'
0x140029c28  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x140029c2c  mov     rax, [rax+70h]
0x140029c30  lea     r9d, [rdx-40h]
0x140029c34  mov     [rsp+0E0h+var_C0], rax
0x140029c39  call    WPP_SF_DSd
0x140029c3e  jmp     loc_140029DBB
0x140029c43  xorps   xmm0, xmm0
0x140029c46  lea     r9, [rbp+3Fh+var_80]; unsigned __int8 *
0x140029c4a  movups  xmmword ptr [rax], xmm0
0x140029c4d  mov     r8, r14; __int64
0x140029c50  mov     rdx, rsi; pvData
0x140029c53  movups  xmmword ptr [rax+0Ch], xmm0
0x140029c57  lea     rax, [rbp+3Fh+var_58]
0x140029c5b  mov     rcx, rdi; this
0x140029c5e  mov     [rsp+0E0h+var_A8], rax; unsigned __int16 *
0x140029c63  lea     rax, [rbp+3Fh+var_7E]
0x140029c67  mov     [rsp+0E0h+var_B0], r12; unsigned __int16 *
0x140029c6c  mov     [rsp+0E0h+var_B8], rax; unsigned __int8 *
0x140029c71  lea     rax, [rbp+3Fh+var_7F]
0x140029c75  mov     [rsp+0E0h+var_C0], rax; unsigned __int8 *
0x140029c7a  call    ?GetHeatRecord@TieringHeatSession@@QEAAJPEAUTE_FILE_ID_128@@_JPEAE22PEAG3@Z; TieringHeatSession::GetHeatRecord(TE_FILE_ID_128 *,__int64,uchar *,uchar *,uchar *,ushort *,ushort *)
0x140029c7f  mov     [rbp+3Fh+var_60], eax
0x140029c82  mov     ebx, eax
0x140029c84  test    eax, eax
0x140029c86  jns     short loc_140029CF0
0x140029c88  mov     rcx, cs:WPP_GLOBAL_Control
0x140029c8f  lea     rax, WPP_GLOBAL_Control
0x140029c96  cmp     rcx, rax
0x140029c99  jz      loc_140029DBB
0x140029c9f  test    byte ptr [rcx+1Ch], 1
0x140029ca3  jz      loc_140029DBB
0x140029ca9  mov     al, 2
0x140029cab  cmp     [rcx+19h], al
0x140029cae  jb      loc_140029DBB
0x140029cb4  mov     rax, [rdi+28h]
0x140029cb8  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140029cbf  mov     r9, [rsi+8]
0x140029cc3  mov     edx, 48h ; 'H'
0x140029cc8  mov     rcx, [rcx+10h]
0x140029ccc  mov     dword ptr [rsp+0E0h+var_A8], ebx
0x140029cd0  mov     rax, [rax+70h]
0x140029cd4  mov     [rsp+0E0h+var_B0], rax
0x140029cd9  mov     rax, [rsi]
0x140029cdc  mov     dword ptr [rsp+0E0h+var_B8], r14d
0x140029ce1  mov     [rsp+0E0h+var_C0], rax
0x140029ce6  call    WPP_SF_iiDSd
0x140029ceb  jmp     loc_140029DBB
0x140029cf0  mov     [rsp+0E0h+var_90], 0; unsigned int *
0x140029cf9  lea     rax, [rbp+3Fh+var_7C]
0x140029cfd  mov     [rsp+0E0h+var_98], r15; unsigned int *
0x140029d02  xor     r9d, r9d; unsigned int
0x140029d05  mov     [rsp+0E0h+var_A0], rax; int *
0x140029d0a  mov     r8, r14; __int64
0x140029d0d  lea     rax, [rbp+3Fh+var_58]
0x140029d11  mov     [rbp+3Fh+var_7C], 0
0x140029d18  mov     [rsp+0E0h+var_A8], rax; unsigned __int16 *
0x140029d1d  mov     rdx, rsi; struct TE_FILE_ID_128 *
0x140029d20  mov     al, [rbp+3Fh+var_7F]
0x140029d23  mov     rcx, rdi; this
0x140029d26  mov     byte ptr [rsp+0E0h+var_B0], al; char
0x140029d2a  movzx   eax, word ptr [r12]
0x140029d2f  mov     word ptr [rsp+0E0h+var_B8], ax; unsigned __int16
0x140029d34  mov     al, [rbp+3Fh+var_7E]
0x140029d37  mov     byte ptr [rsp+0E0h+var_C0], al; char
0x140029d3b  call    ?AddCurrentCountAndAgeHistory@TieringHeatSession@@QEAAXPEBUTE_FILE_ID_128@@_JKEGEPEAGPEAHPEAK4@Z; TieringHeatSession::AddCurrentCountAndAgeHistory(TE_FILE_ID_128 const *,__int64,ulong,uchar,ushort,uchar,ushort *,int *,ulong *,ulong *)
0x140029d40  movzx   r8d, [rbp+3Fh+var_7F]
0x140029d45  test    r8b, 8
0x140029d49  jz      short loc_140029D4F
0x140029d4b  mov     al, 1
0x140029d4d  jmp     short loc_140029D7C
0x140029d4f  test    r8b, 4
0x140029d53  jz      short loc_140029D59
0x140029d55  mov     al, 2
0x140029d57  jmp     short loc_140029D7C
0x140029d59  test    [rbp+3Fh+var_80], 10h
0x140029d5d  mov     rax, [rdi+28h]
0x140029d61  mov     ecx, [r15]
0x140029d64  mov     rdx, [rax]
0x140029d67  jz      short loc_140029D71
0x140029d69  cmp     ecx, [rdx+0E4h]
0x140029d6f  jmp     short loc_140029D77
0x140029d71  cmp     ecx, [rdx+0E0h]
0x140029d77  setb    al
0x140029d7a  inc     al
0x140029d7c  or      al, [rbp+3Fh+var_80]
0x140029d7f  movzx   ecx, [rbp+3Fh+var_7E]
0x140029d83  movzx   edx, al
0x140029d86  mov     rax, [rbp+3Fh+var_78]
0x140029d8a  shl     ecx, 8
0x140029d8d  or      ecx, r8d
0x140029d90  mov     [rbp+3Fh+var_80], dl
0x140029d93  shl     ecx, 8
0x140029d96  or      ecx, edx
0x140029d98  mov     [rax], ecx
0x140029d9a  mov     rax, [rbp+3Fh+var_70]
0x140029d9e  mov     dword ptr [rax], 7
0x140029da4  xor     eax, eax
0x140029da6  movzx   edx, [rbp+rax*2+3Fh+var_58]
0x140029dab  mov     rcx, [r13+0]
0x140029daf  mov     [rcx+rax*4], edx
0x140029db2  inc     rax
0x140029db5  cmp     rax, 7
0x140029db9  jnz     short loc_140029DA6
0x140029dbb  lea     rcx, [rbp+3Fh+var_68]; this
0x140029dbf  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140029dc4  mov     eax, ebx
0x140029dc6  mov     rcx, [rbp+3Fh+var_48]
0x140029dca  xor     rcx, rsp; StackCookie
0x140029dcd  call    __security_check_cookie
0x140029dd2  add     rsp, 0A8h
0x140029dd9  pop     r15
0x140029ddb  pop     r14
0x140029ddd  pop     r13
0x140029ddf  pop     r12
0x140029de1  pop     rdi
0x140029de2  pop     rsi
0x140029de3  pop     rbx
0x140029de4  pop     rbp
0x140029de5  retn
```
