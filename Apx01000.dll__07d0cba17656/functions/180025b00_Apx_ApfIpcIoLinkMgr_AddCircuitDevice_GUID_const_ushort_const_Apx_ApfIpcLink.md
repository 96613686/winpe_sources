# Apx::ApfIpcIoLinkMgr::AddCircuitDevice(_GUID const *,ushort const *,Apx::ApfIpcLink * *)

- ea: `0x180025b00`
- end: `0x180025dd1`
- name: `?AddCircuitDevice@ApfIpcIoLinkMgr@Apx@@UEAAJPEBU_GUID@@PEBGPEAPEAVApfIpcLink@2@@Z`
- size: `721`
- prototype: `__int64 __fastcall(unsigned __int64 this, const struct _GUID *, const unsigned __int16 *, struct Apx::ApfIpcLink **)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001d30`
- `0x1800027c8`
- `0x18000a12c`
- `0x18000ba84`
- `0x18000d210`
- `0x18000d2f0`
- `0x18001051c`
- `0x180025b00`
- `0x180026c98`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025d7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025d7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025b95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025b95`

## string_xrefs

- `0x180025d53`: `onecoreuap\drivers\wdm\audio\backpln\apx\class\ipclinks\apfipciolinkmgr.cpp`

## pseudocode

```c
__int64 __fastcall Apx::ApfIpcIoLinkMgr::AddCircuitDevice(
        unsigned __int64 this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        struct Apx::ApfIpcLink **a4)
{
  __int64 v8; // rdx
  __int64 v9; // xmm0_8
  char *v10; // r8
  __int64 v11; // rax
  char *v12; // rcx
  signed int v13; // ebx
  int v14; // eax
  unsigned __int64 v15; // rdx
  unsigned __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  struct Apx::ApfIpcLink *v18; // [rsp+58h] [rbp-A8h] BYREF
  DWORD NumberOfBytesTransferred[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int Data1; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+74h] [rbp-8Ch] BYREF
  int v22; // [rsp+7Ch] [rbp-84h]
  char v23; // [rsp+84h] [rbp-7Ch] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
  v18 = 0;
  NumberOfBytesTransferred[0] = 0;
  Data1 = 0;
  memset_0(&v21, 0, 0xB0u);
  v17 = 0;
  *a4 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
  v8 = 80;
  v9 = *(_QWORD *)&a2->Data2;
  v10 = &v23;
  Data1 = a2->Data1;
  v22 = *(_DWORD *)&a2->Data4[4];
  v11 = 2147483646;
  v21 = v9;
  do
  {
    if ( !v11 )
      break;
    if ( !*a3 )
      break;
    *(_WORD *)v10 = *a3++;
    v10 += 2;
    --v11;
    --v8;
  }
  while ( v8 );
  v12 = v10 - 2;
  v13 = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v12 = v10;
  *(_WORD *)v12 = 0;
  if ( v8 )
  {
    v14 = Apx::ApfHelper::SyncIoctl(
            *(void **)(this + 88),
            0x1388u,
            0x1DC000u,
            &Data1,
            0xB4u,
            &v17,
            8u,
            NumberOfBytesTransferred,
            0);
    v13 = v14;
    if ( v14 >= 0 )
    {
      v15 = v17;
      if ( !v17 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            64,
            &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids,
            ~this,
            v14);
          v15 = v17;
        }
        v13 = -2147467259;
        goto LABEL_26;
      }
      v13 = (*(__int64 (__fastcall **)(unsigned __int64, unsigned __int64, struct Apx::ApfIpcLink **))(*(_QWORD *)this + 64LL))(
              this,
              v17,
              &v18);
      if ( v13 >= 0 )
      {
        v13 = 0;
        *a4 = v18;
        goto LABEL_30;
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && *((char *)WPP_GLOBAL_Control + 28) < 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids,
      ~this,
      -2147024774);
  }
  v15 = v17;
LABEL_26:
  if ( v15 )
    Apx::ApfIpcIoLinkMgr::RemoveCircuitDevice((Apx::ApfIpcIoLinkMgr *)this, v15);
  if ( v18 )
  {
    imp_ApxObjectDelete(0, (Apx::ApfVerify *)~(unsigned __int64)v18);
    imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~(unsigned __int64)v18);
    v18 = 0;
  }
LABEL_30:
  LeaveCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180025b00  push    rbp
0x180025b02  push    rbx
0x180025b03  push    rsi
0x180025b04  push    rdi
0x180025b05  push    r12
0x180025b07  push    r14
0x180025b09  push    r15
0x180025b0b  lea     rbp, [rsp-40h]
0x180025b10  sub     rsp, 140h
0x180025b17  mov     rax, cs:__security_cookie
0x180025b1e  xor     rax, rsp
0x180025b21  mov     [rbp+70h+var_40], rax
0x180025b25  mov     r14, r9
0x180025b28  mov     rbx, r8
0x180025b2b  mov     rsi, rdx
0x180025b2e  mov     rdi, rcx
0x180025b31  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b38  lea     rax, WPP_GLOBAL_Control
0x180025b3f  cmp     rcx, rax
0x180025b42  jz      short loc_180025B65
0x180025b44  test    byte ptr [rcx+1Ch], 1
0x180025b48  jz      short loc_180025B65
0x180025b4a  cmp     byte ptr [rcx+19h], 5
0x180025b4e  jb      short loc_180025B65
0x180025b50  mov     rcx, [rcx+10h]
0x180025b54  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180025b5b  mov     edx, 3Eh ; '>'
0x180025b60  call    WPP_SF_
0x180025b65  xor     r12d, r12d
0x180025b68  lea     rcx, [rsp+170h+var_FC]; void *
0x180025b6d  xor     edx, edx; Val
0x180025b6f  mov     [rsp+170h+var_118], r12
0x180025b74  mov     r8d, 0B0h; Size
0x180025b7a  mov     [rsp+170h+NumberOfBytesTransferred], r12d
0x180025b7f  mov     [rsp+170h+var_100], r12d
0x180025b84  call    memset_0
0x180025b89  lea     rcx, [rdi+10h]; lpCriticalSection
0x180025b8d  mov     [rsp+170h+var_120], r12
0x180025b92  mov     [r14], r12
0x180025b95  call    cs:__imp_EnterCriticalSection
0x180025b9b  mov     eax, [rsi]
0x180025b9d  lea     edx, [r12+50h]
0x180025ba2  movsd   xmm0, qword ptr [rsi+4]
0x180025ba7  lea     r8, [rbp+70h+var_EC]
0x180025bab  mov     [rsp+170h+var_100], eax
0x180025baf  mov     eax, [rsi+0Ch]
0x180025bb2  mov     [rsp+170h+var_F4], eax
0x180025bb6  mov     eax, 7FFFFFFEh
0x180025bbb  movsd   [rsp+170h+var_FC], xmm0
0x180025bc1  test    rax, rax
0x180025bc4  jz      short loc_180025BE3
0x180025bc6  movzx   ecx, word ptr [rbx]
0x180025bc9  test    cx, cx
0x180025bcc  jz      short loc_180025BE3
0x180025bce  mov     [r8], cx
0x180025bd2  add     rbx, 2
0x180025bd6  add     r8, 2
0x180025bda  dec     rax
0x180025bdd  sub     rdx, 1
0x180025be1  jnz     short loc_180025BC1
0x180025be3  mov     rax, rdx
0x180025be6  lea     rcx, [r8-2]
0x180025bea  neg     rax
0x180025bed  sbb     ebx, ebx
0x180025bef  not     ebx
0x180025bf1  and     ebx, 8007007Ah
0x180025bf7  test    rdx, rdx
0x180025bfa  cmovnz  rcx, r8
0x180025bfe  mov     [rcx], r12w
0x180025c02  jnz     short loc_180025C53
0x180025c04  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c0b  lea     rsi, WPP_GLOBAL_Control
0x180025c12  cmp     rcx, rsi
0x180025c15  jz      loc_180025D28
0x180025c1b  test    byte ptr [rcx+1Ch], 80h
0x180025c1f  jz      loc_180025D28
0x180025c25  cmp     byte ptr [rcx+19h], 2
0x180025c29  jb      loc_180025D28
0x180025c2f  mov     rcx, [rcx+10h]
0x180025c33  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180025c3a  mov     r9, rdi
0x180025c3d  mov     [rsp+170h+nInBufferSize], ebx
0x180025c41  not     r9
0x180025c44  mov     edx, 3Fh ; '?'
0x180025c49  call    WPP_SF_qd
0x180025c4e  jmp     loc_180025D28
0x180025c53  mov     rcx, [rdi+58h]; void *
0x180025c57  lea     rax, [rsp+170h+NumberOfBytesTransferred]
0x180025c5c  mov     [rsp+170h+var_130], r12; void *
0x180025c61  lea     r9, [rsp+170h+var_100]; void *
0x180025c66  mov     [rsp+170h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180025c6b  mov     edx, 1388h; unsigned int
0x180025c70  lea     rax, [rsp+170h+var_120]
0x180025c75  mov     [rsp+170h+var_140], 8; DWORD
0x180025c7d  mov     [rsp+170h+var_148], rax; void *
0x180025c82  mov     r8d, 1DC000h; unsigned int
0x180025c88  mov     [rsp+170h+nInBufferSize], 0B4h; nInBufferSize
0x180025c90  call    ?SyncIoctl@ApfHelper@Apx@@SAJPEAXKK0K0KPEAK0@Z; Apx::ApfHelper::SyncIoctl(void *,ulong,ulong,void *,ulong,void *,ulong,ulong *,void *)
0x180025c95  mov     ebx, eax
0x180025c97  test    eax, eax
0x180025c99  js      loc_180025D21
0x180025c9f  mov     rdx, [rsp+170h+var_120]
0x180025ca4  test    rdx, rdx
0x180025ca7  jnz     short loc_180025CF3
0x180025ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cb0  lea     rsi, WPP_GLOBAL_Control
0x180025cb7  cmp     rcx, rsi
0x180025cba  jz      short loc_180025CEC
0x180025cbc  test    byte ptr [rcx+1Ch], 80h
0x180025cc0  jz      short loc_180025CEC
0x180025cc2  cmp     byte ptr [rcx+19h], 2
0x180025cc6  jb      short loc_180025CEC
0x180025cc8  mov     rcx, [rcx+10h]
0x180025ccc  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180025cd3  mov     r9, rdi
0x180025cd6  mov     [rsp+170h+nInBufferSize], eax
0x180025cda  not     r9
0x180025cdd  mov     edx, 40h ; '@'
0x180025ce2  call    WPP_SF_qd
0x180025ce7  mov     rdx, [rsp+170h+var_120]
0x180025cec  mov     ebx, 80004005h
0x180025cf1  jmp     short loc_180025D2D
0x180025cf3  mov     rax, [rdi]
0x180025cf6  lea     r8, [rsp+170h+var_118]
0x180025cfb  mov     rcx, rdi
0x180025cfe  mov     rax, [rax+40h]
0x180025d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d07  lea     rsi, WPP_GLOBAL_Control
0x180025d0e  mov     ebx, eax
0x180025d10  test    eax, eax
0x180025d12  js      short loc_180025D28
0x180025d14  mov     rax, [rsp+170h+var_118]
0x180025d19  mov     ebx, r12d
0x180025d1c  mov     [r14], rax
0x180025d1f  jmp     short loc_180025D7A
0x180025d21  lea     rsi, WPP_GLOBAL_Control
0x180025d28  mov     rdx, [rsp+170h+var_120]; unsigned __int64
0x180025d2d  test    rdx, rdx
0x180025d30  jz      short loc_180025D3A
0x180025d32  mov     rcx, rdi; this
0x180025d35  call    ?RemoveCircuitDevice@ApfIpcIoLinkMgr@Apx@@AEAAX_K@Z; Apx::ApfIpcIoLinkMgr::RemoveCircuitDevice(unsigned __int64)
0x180025d3a  mov     rdx, [rsp+170h+var_118]
0x180025d3f  test    rdx, rdx
0x180025d42  jz      short loc_180025D7A
0x180025d44  not     rdx; Apx::ApfVerify *
0x180025d47  xor     ecx, ecx; this
0x180025d49  call    imp_ApxObjectDelete
0x180025d4e  mov     rdx, [rsp+170h+var_118]
0x180025d53  lea     rax, aOnecoreuapDriv_4; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180025d5a  not     rdx; Apx::ApfVerify *
0x180025d5d  mov     qword ptr [rsp+170h+nInBufferSize], rax
0x180025d62  xor     ecx, ecx; this
0x180025d64  mov     r9d, 381h
0x180025d6a  mov     r8d, 44787041h
0x180025d70  call    imp_ApxObjectDereferenceActual
0x180025d75  mov     [rsp+170h+var_118], r12
0x180025d7a  lea     rcx, [rdi+10h]; lpCriticalSection
0x180025d7e  call    cs:__imp_LeaveCriticalSection
0x180025d84  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d8b  cmp     rcx, rsi
0x180025d8e  jz      short loc_180025DB1
0x180025d90  test    byte ptr [rcx+1Ch], 1
0x180025d94  jz      short loc_180025DB1
0x180025d96  cmp     byte ptr [rcx+19h], 5
0x180025d9a  jb      short loc_180025DB1
0x180025d9c  mov     rcx, [rcx+10h]
0x180025da0  lea     r8, WPP_e6720f2ec66938db1e8abec7a65481bb_Traceguids
0x180025da7  mov     edx, 41h ; 'A'
0x180025dac  call    WPP_SF_
0x180025db1  mov     eax, ebx
0x180025db3  mov     rcx, [rbp+70h+var_40]
0x180025db7  xor     rcx, rsp; StackCookie
0x180025dba  call    __security_check_cookie
0x180025dbf  add     rsp, 140h
0x180025dc6  pop     r15
0x180025dc8  pop     r14
0x180025dca  pop     r12
0x180025dcc  pop     rdi
0x180025dcd  pop     rsi
0x180025dce  pop     rbx
0x180025dcf  pop     rbp
0x180025dd0  retn
```
