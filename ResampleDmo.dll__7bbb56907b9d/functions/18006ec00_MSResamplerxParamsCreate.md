# MSResamplerxParamsCreate

- ea: `0x18006ec00`
- end: `0x18006ece4`
- name: `MSResamplerxParamsCreate`
- size: `228`
- prototype: `CRSxHandle *__fastcall(struct WAVEFORMATEXTENSIBLE *, struct WAVEFORMATEXTENSIBLE *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18006eab0`

## callees

- `0x18000abb4`
- `0x18006dd10`
- `0x18006ea80`
- `0x18006ec00`
- `0x18006edb0`

## pseudocode

```c
CRSxHandle *__fastcall MSResamplerxParamsCreate(
        struct WAVEFORMATEXTENSIBLE *a1,
        struct WAVEFORMATEXTENSIBLE *a2,
        __int64 a3)
{
  CRSxHandle *v6; // rax
  CRSxHandle *v7; // rdi
  __int64 *v8; // rax
  unsigned int v9; // edx
  __int64 *v10; // rbx
  __int64 v11; // rax
  int v12; // xmm0_4
  int v13; // r9d
  __int64 v15; // [rsp+20h] [rbp-58h]
  __int128 v16; // [rsp+40h] [rbp-38h] BYREF

  v6 = (CRSxHandle *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    *(_DWORD *)v6 = -863945167;
    *((_QWORD *)v6 + 1) = 0;
    v8 = (__int64 *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *v8 = 0;
    }
    else
    {
      v10 = 0;
    }
    *((_QWORD *)v7 + 1) = v10;
    if ( v10 )
    {
      if ( a3 )
      {
        v11 = *(_QWORD *)(a3 + 8);
        v12 = *(_DWORD *)(a3 + 4);
        v13 = *(_DWORD *)a3;
      }
      else
      {
        v16 = 0;
        MSResamplerxSetDefaultParams(a1, a2, &v16);
        v11 = *((_QWORD *)&v16 + 1);
        v12 = DWORD1(v16);
        v13 = v16;
      }
      LODWORD(v15) = v12;
      if ( !(unsigned int)NResampler::init(v10, a1, a2, v13, v15, v11) )
        return v7;
    }
    CRSxHandle::`scalar deleting destructor'(v7, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18006ec00  push    rbx
0x18006ec02  push    rbp
0x18006ec03  push    rsi
0x18006ec04  push    rdi
0x18006ec05  push    r14
0x18006ec07  sub     rsp, 50h
0x18006ec0b  mov     rbp, rdx
0x18006ec0e  mov     r14, rcx
0x18006ec11  mov     ebx, 10h
0x18006ec16  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006ec1d  mov     ecx, ebx; unsigned __int64
0x18006ec1f  mov     rsi, r8
0x18006ec22  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006ec27  mov     rdi, rax
0x18006ec2a  test    rax, rax
0x18006ec2d  jz      loc_18006ECD7
0x18006ec33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006ec3a  mov     dword ptr [rax], 0CC813E31h
0x18006ec40  mov     ecx, ebx; unsigned __int64
0x18006ec42  mov     qword ptr [rax+8], 0
0x18006ec4a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006ec4f  mov     rbx, rax
0x18006ec52  test    rax, rax
0x18006ec55  jz      short loc_18006EC67
0x18006ec57  mov     dword ptr [rax+8], 0
0x18006ec5e  mov     qword ptr [rax], 0
0x18006ec65  jmp     short loc_18006EC69
0x18006ec67  xor     ebx, ebx
0x18006ec69  mov     [rdi+8], rbx
0x18006ec6d  test    rbx, rbx
0x18006ec70  jz      short loc_18006ECCF
0x18006ec72  test    rsi, rsi
0x18006ec75  jnz     short loc_18006ECA1
0x18006ec77  xorps   xmm0, xmm0
0x18006ec7a  lea     r8, [rsp+78h+var_38]
0x18006ec7f  mov     rdx, rbp
0x18006ec82  mov     rcx, r14
0x18006ec85  movups  [rsp+78h+var_38], xmm0
0x18006ec8a  call    MSResamplerxSetDefaultParams
0x18006ec8f  mov     rax, qword ptr [rsp+78h+var_38+8]
0x18006ec94  movss   xmm0, dword ptr [rsp+78h+var_38+4]
0x18006ec9a  mov     r9d, dword ptr [rsp+78h+var_38]
0x18006ec9f  jmp     short loc_18006ECAD
0x18006eca1  mov     rax, [rsi+8]
0x18006eca5  movss   xmm0, dword ptr [rsi+4]
0x18006ecaa  mov     r9d, [rsi]
0x18006ecad  mov     [rsp+78h+var_50], rax
0x18006ecb2  mov     r8, rbp
0x18006ecb5  mov     rdx, r14
0x18006ecb8  movss   dword ptr [rsp+78h+var_58], xmm0
0x18006ecbe  mov     rcx, rbx
0x18006ecc1  call    ?init@NResampler@@QEAAJPEAUWAVEFORMATEXTENSIBLE@@0HMPEAMPEAV?$shared_ptr@UIAudioSignalProcessingStateBufferAllocator@@@std@@PEAV?$shared_ptr@UIAudioSignalProcessingScratchBufferAllocator@@@4@@Z; NResampler::init(WAVEFORMATEXTENSIBLE *,WAVEFORMATEXTENSIBLE *,int,float,float *,std::shared_ptr<IAudioSignalProcessingStateBufferAllocator> *,std::shared_ptr<IAudioSignalProcessingScratchBufferAllocator> *)
0x18006ecc6  test    eax, eax
0x18006ecc8  jnz     short loc_18006ECCF
0x18006ecca  mov     rax, rdi
0x18006eccd  jmp     short loc_18006ECD9
0x18006eccf  mov     rcx, rdi; this
0x18006ecd2  call    ??_GCRSxHandle@@QEAAPEAXI@Z; CRSxHandle::`scalar deleting destructor'(uint)
0x18006ecd7  xor     eax, eax
0x18006ecd9  add     rsp, 50h
0x18006ecdd  pop     r14
0x18006ecdf  pop     rdi
0x18006ece0  pop     rsi
0x18006ece1  pop     rbp
0x18006ece2  pop     rbx
0x18006ece3  retn
```
