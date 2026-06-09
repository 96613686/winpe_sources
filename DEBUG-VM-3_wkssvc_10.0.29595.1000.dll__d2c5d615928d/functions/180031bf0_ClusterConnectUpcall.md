# ClusterConnectUpcall

- ea: `0x180031bf0`
- end: `0x180031db9`
- name: `ClusterConnectUpcall`
- size: `457`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b76c`
- `0x18000dd68`
- `0x18001e420`
- `0x180022b7c`
- `0x180031bf0`
- `0x180033159`
- `0x180034010`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180031c44`
- `ntdll!RtlAcquireResourceShared` at `0x180031c44`
- `ntdll!RtlReleaseResource` at `0x180031d78`
- `ntdll!RtlReleaseResource` at `0x180031d78`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180031d33`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180031d33`

## pseudocode

```c
void __fastcall ClusterConnectUpcall(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        const void **a3,
        const void **a4,
        __int64 a5,
        __int128 *a6,
        int a7)
{
  _WORD *v10; // rdi
  _WORD *v11; // rax
  _WORD *v12; // rbx
  unsigned int v13; // eax
  void *v14; // rax
  unsigned int v15; // eax
  unsigned int Reply; // [rsp+30h] [rbp-48h] BYREF
  __int128 v17; // [rsp+38h] [rbp-40h] BYREF

  Reply = 0;
  v10 = 0;
  v17 = *a6;
  RtlAcquireResourceShared(&UpcallServerResource, 1u);
  if ( UpcallServerState == 1 )
  {
    v11 = MemoryAlloc(*(unsigned __int16 *)a3 + 2LL);
    v12 = v11;
    if ( v11
      && (memcpy_0(v11, a3[1], *(unsigned __int16 *)a3),
          v12[(unsigned __int64)*(unsigned __int16 *)a3 >> 1] = 0,
          v14 = MemoryAlloc(*(unsigned __int16 *)a4 + 2LL),
          (v10 = v14) != 0) )
    {
      memcpy_0(v14, a4[1], *(unsigned __int16 *)a4);
      v10[(unsigned __int64)*(unsigned __int16 *)a4 >> 1] = 0;
      v13 = (*(__int64 (__fastcall **)(_WORD *, _WORD *, __int64, __int128 *, int))pUpcallDispatch)(
              v12,
              v10,
              a5,
              &v17,
              a7);
    }
    else
    {
      v13 = 14;
    }
  }
  else
  {
    v12 = 0;
    v13 = 87;
  }
  Reply = v13;
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 24, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v13);
  }
  v15 = RpcAsyncCompleteCall(pAsync, &Reply);
  Reply = v15;
  if ( v15
    && WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 25, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids, v15);
  }
  RtlReleaseResource(&UpcallServerResource);
  if ( v12 )
    MemoryFree(v12);
  if ( v10 )
    MemoryFree(v10);
}

```

## disassembly

```asm
0x180031bf0  mov     [rsp+arg_8], rbx
0x180031bf5  push    rbp
0x180031bf6  push    rsi
0x180031bf7  push    rdi
0x180031bf8  push    r14
0x180031bfa  push    r15
0x180031bfc  sub     rsp, 50h
0x180031c00  mov     rax, cs:__security_cookie
0x180031c07  xor     rax, rsp
0x180031c0a  mov     [rsp+78h+var_30], rax
0x180031c0f  mov     rax, [rsp+78h+arg_28]
0x180031c17  mov     r14, rcx
0x180031c1a  mov     r15, [rsp+78h+arg_20]
0x180031c22  lea     rcx, UpcallServerResource; Resource
0x180031c29  mov     dl, 1; Wait
0x180031c2b  mov     [rsp+78h+Reply], 0
0x180031c33  mov     rbp, r9
0x180031c36  mov     rsi, r8
0x180031c39  movups  xmm0, xmmword ptr [rax]
0x180031c3c  xor     edi, edi
0x180031c3e  movdqu  [rsp+78h+var_40], xmm0
0x180031c44  call    cs:__imp_RtlAcquireResourceShared
0x180031c4a  cmp     cs:UpcallServerState, 1
0x180031c51  jnz     loc_180031CEB
0x180031c57  movzx   ecx, word ptr [rsi]
0x180031c5a  add     rcx, 2; unsigned __int64
0x180031c5e  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x180031c63  mov     rbx, rax
0x180031c66  test    rax, rax
0x180031c69  jnz     short loc_180031C72
0x180031c6b  mov     eax, 0Eh
0x180031c70  jmp     short loc_180031CF0
0x180031c72  movzx   r8d, word ptr [rsi]; Size
0x180031c76  mov     rcx, rbx; void *
0x180031c79  mov     rdx, [rsi+8]; Src
0x180031c7d  call    memcpy_0
0x180031c82  movzx   ecx, word ptr [rsi]
0x180031c85  xor     eax, eax
0x180031c87  shr     rcx, 1
0x180031c8a  mov     [rbx+rcx*2], ax
0x180031c8e  movzx   ecx, word ptr [rbp+0]
0x180031c92  add     rcx, 2; unsigned __int64
0x180031c96  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x180031c9b  mov     rdi, rax
0x180031c9e  test    rax, rax
0x180031ca1  jz      short loc_180031C6B
0x180031ca3  movzx   r8d, word ptr [rbp+0]; Size
0x180031ca8  mov     rcx, rax; void *
0x180031cab  mov     rdx, [rbp+8]; Src
0x180031caf  call    memcpy_0
0x180031cb4  movzx   ecx, word ptr [rbp+0]
0x180031cb8  lea     r9, [rsp+78h+var_40]
0x180031cbd  shr     rcx, 1
0x180031cc0  xor     eax, eax
0x180031cc2  mov     r8, r15
0x180031cc5  mov     rdx, rdi
0x180031cc8  mov     [rdi+rcx*2], ax
0x180031ccc  mov     rax, cs:pUpcallDispatch
0x180031cd3  mov     ecx, [rsp+78h+arg_30]
0x180031cda  mov     [rsp+78h+var_58], ecx
0x180031cde  mov     rcx, rbx
0x180031ce1  mov     rax, [rax]
0x180031ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ce9  jmp     short loc_180031CF0
0x180031ceb  xor     ebx, ebx
0x180031ced  lea     eax, [rbx+57h]
0x180031cf0  mov     [rsp+78h+Reply], eax
0x180031cf4  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180031cfb  lea     rsi, WPP_witness_GLOBAL_Control
0x180031d02  cmp     rcx, rsi
0x180031d05  jz      short loc_180031D2B
0x180031d07  test    byte ptr [rcx+1Ch], 1
0x180031d0b  jz      short loc_180031D2B
0x180031d0d  cmp     byte ptr [rcx+19h], 3
0x180031d11  jb      short loc_180031D2B
0x180031d13  mov     rcx, [rcx+10h]
0x180031d17  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x180031d1e  mov     edx, 18h
0x180031d23  mov     r9d, eax
0x180031d26  call    WPP_SF_d
0x180031d2b  lea     rdx, [rsp+78h+Reply]; Reply
0x180031d30  mov     rcx, r14; pAsync
0x180031d33  call    cs:__imp_RpcAsyncCompleteCall
0x180031d39  mov     [rsp+78h+Reply], eax
0x180031d3d  test    eax, eax
0x180031d3f  jz      short loc_180031D71
0x180031d41  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180031d48  cmp     rcx, rsi
0x180031d4b  jz      short loc_180031D71
0x180031d4d  test    byte ptr [rcx+1Ch], 1
0x180031d51  jz      short loc_180031D71
0x180031d53  cmp     byte ptr [rcx+19h], 1
0x180031d57  jb      short loc_180031D71
0x180031d59  mov     rcx, [rcx+10h]
0x180031d5d  lea     r8, WPP_25b73f0a37193b70b6a932c4d871ce72_Traceguids
0x180031d64  mov     edx, 19h
0x180031d69  mov     r9d, eax
0x180031d6c  call    WPP_SF_d
0x180031d71  lea     rcx, UpcallServerResource; Resource
0x180031d78  call    cs:__imp_RtlReleaseResource
0x180031d7e  test    rbx, rbx
0x180031d81  jz      short loc_180031D8B
0x180031d83  mov     rcx, rbx; void *
0x180031d86  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180031d8b  test    rdi, rdi
0x180031d8e  jz      short loc_180031D98
0x180031d90  mov     rcx, rdi; void *
0x180031d93  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180031d98  mov     rcx, [rsp+78h+var_30]
0x180031d9d  xor     rcx, rsp; StackCookie
0x180031da0  call    __security_check_cookie
0x180031da5  mov     rbx, [rsp+78h+arg_8]
0x180031dad  add     rsp, 50h
0x180031db1  pop     r15
0x180031db3  pop     r14
0x180031db5  pop     rdi
0x180031db6  pop     rsi
0x180031db7  pop     rbp
0x180031db8  retn
```
