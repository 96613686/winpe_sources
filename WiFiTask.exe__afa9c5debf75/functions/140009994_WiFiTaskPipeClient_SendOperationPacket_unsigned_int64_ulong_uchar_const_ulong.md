# WiFiTaskPipeClient::SendOperationPacket(unsigned __int64,ulong,uchar const *,ulong)

- ea: `0x140009994`
- end: `0x140009b45`
- name: `?SendOperationPacket@WiFiTaskPipeClient@@QEAAJ_KKPEBEK@Z`
- size: `433`
- prototype: `__int64 __fastcall(WiFiTaskPipeClient *this, __int64, int, const unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x140006b40`
- `0x140006eb0`
- `0x14000a4a0`

## callees

- `0x1400016a0`
- `0x1400016d0`
- `0x140002168`
- `0x140009994`
- `0x14000bfb8`
- `0x14000c1a4`
- `0x14000d184`
- `0x14000e4cc`
- `0x140010df8`

## pseudocode

```c
__int64 __fastcall WiFiTaskPipeClient::SendOperationPacket(
        WiFiTaskPipeClient *this,
        __int64 a2,
        int a3,
        const unsigned __int8 *a4,
        unsigned int a5)
{
  WiFiTaskPipeClient *v8; // rbx
  unsigned int v9; // r14d
  unsigned int v10; // eax
  Synchronizer **v11; // rsi
  _QWORD *v12; // rdi
  char *v13; // rbx
  void *v15; // [rsp+28h] [rbp-D8h]
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  WiFiTaskPipeClient *v17; // [rsp+48h] [rbp-B8h]
  _QWORD *v18; // [rsp+50h] [rbp-B0h]
  __int64 Src; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+68h] [rbp-98h]
  BOOL v21; // [rsp+6Ch] [rbp-94h]
  unsigned int v22; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Destination[1004]; // [rsp+74h] [rbp-8Ch] BYREF

  v8 = this;
  v17 = this;
  Src = a2;
  v20 = a3;
  v21 = 0;
  memset_0(&v22, 0, 0x3F0u);
  v9 = 0;
  do
  {
    v10 = a5 - v9;
    if ( a5 - v9 > 0x3E8 )
      v10 = 1000;
    v22 = v10;
    if ( v10 )
    {
      memcpy_s(Destination, 0x3E8u, &a4[v9], v10);
      v10 = v22;
    }
    v9 += v10;
    v21 = v9 >= a5;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LODWORD(v15) = v10;
      WPP_SF_IDdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9 >= a5, &WPP_GLOBAL_Control, a2, a3);
    }
    v11 = (Synchronizer **)*((_QWORD *)v8 + 2);
    v12 = operator new(0x18u);
    v18 = v12;
    *v12 = 0;
    v12[1] = 0;
    v12[2] = 0;
    v13 = (char *)operator new(0x400u);
    *v12 = v13;
    v12[1] = v13;
    v12[2] = v13 + 1024;
    memmove_0(v13, &Src, 0x400u);
    v12[1] = v13 + 1024;
    v16 = 0;
    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v16);
    Synchronizer::EnqueueEvent(v11[1], (struct SynchronizedObject *)v11, 2, v12, 0, v15);
    v8 = v17;
  }
  while ( !v21 );
  return 0;
}

```

## disassembly

```asm
0x140009994  push    rbp
0x140009996  push    rbx
0x140009997  push    rsi
0x140009998  push    rdi
0x140009999  push    r12
0x14000999b  push    r13
0x14000999d  push    r14
0x14000999f  push    r15
0x1400099a1  lea     rbp, [rsp-378h]
0x1400099a9  sub     rsp, 478h
0x1400099b0  mov     rax, cs:__security_cookie
0x1400099b7  xor     rax, rsp
0x1400099ba  mov     [rbp+3B0h+var_50], rax
0x1400099c1  mov     r13, r9
0x1400099c4  mov     r12d, r8d
0x1400099c7  mov     r15, rdx
0x1400099ca  mov     rbx, rcx
0x1400099cd  mov     [rsp+4B0h+var_468], rcx
0x1400099d2  mov     [rsp+4B0h+Src], rdx
0x1400099d7  mov     [rsp+4B0h+var_448], r8d
0x1400099dc  mov     [rsp+4B0h+var_444], 0
0x1400099e4  xor     edx, edx; Val
0x1400099e6  mov     r8d, 3F0h; Size
0x1400099ec  lea     rcx, [rsp+4B0h+var_440]; void *
0x1400099f1  call    memset_0
0x1400099f6  xor     r14d, r14d
0x1400099f9  mov     ecx, 3E8h
0x1400099fe  mov     eax, [rbp+3B0h+arg_20]
0x140009a04  sub     eax, r14d
0x140009a07  cmp     eax, ecx
0x140009a09  cmova   eax, ecx
0x140009a0c  mov     [rsp+4B0h+var_440], eax
0x140009a10  test    eax, eax
0x140009a12  jz      short loc_140009A2E
0x140009a14  mov     r9d, eax; SourceSize
0x140009a17  mov     r8d, r14d
0x140009a1a  add     r8, r13; Source
0x140009a1d  mov     rdx, rcx; DestinationSize
0x140009a20  lea     rcx, [rsp+4B0h+Destination]; Destination
0x140009a25  call    memcpy_s
0x140009a2a  mov     eax, [rsp+4B0h+var_440]
0x140009a2e  add     r14d, eax
0x140009a31  xor     edx, edx
0x140009a33  cmp     r14d, [rbp+3B0h+arg_20]
0x140009a3a  setnb   dl
0x140009a3d  mov     [rsp+4B0h+var_444], edx
0x140009a41  lea     r8, WPP_GLOBAL_Control
0x140009a48  mov     rcx, cs:WPP_GLOBAL_Control
0x140009a4f  cmp     rcx, r8
0x140009a52  jz      short loc_140009A79
0x140009a54  cmp     byte ptr [rcx+19h], 5
0x140009a58  jb      short loc_140009A79
0x140009a5a  test    byte ptr [rcx+1Ch], 1
0x140009a5e  jz      short loc_140009A79
0x140009a60  mov     [rsp+4B0h+var_480], edx
0x140009a64  mov     dword ptr [rsp+4B0h+var_488], eax; void *
0x140009a68  mov     dword ptr [rsp+4B0h+var_490], r12d
0x140009a6d  mov     r9, r15
0x140009a70  mov     rcx, [rcx+10h]
0x140009a74  call    WPP_SF_IDdd
0x140009a79  mov     rsi, [rbx+10h]
0x140009a7d  mov     ecx, 18h; Size
0x140009a82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009a87  mov     rdi, rax
0x140009a8a  mov     [rsp+4B0h+var_460], rax
0x140009a8f  xor     eax, eax
0x140009a91  mov     [rdi], rax
0x140009a94  mov     [rdi+8], rax
0x140009a98  mov     [rdi+10h], rax
0x140009a9c  mov     ecx, 400h; Size
0x140009aa1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009aa6  mov     rbx, rax
0x140009aa9  mov     [rdi], rax
0x140009aac  mov     [rdi+8], rax
0x140009ab0  lea     rcx, [rax+400h]
0x140009ab7  mov     [rdi+10h], rcx
0x140009abb  mov     r8d, 400h; Size
0x140009ac1  lea     rdx, [rsp+4B0h+Src]; Src
0x140009ac6  mov     rcx, rax; void *
0x140009ac9  call    memmove_0
0x140009ace  lea     rax, [rbx+400h]
0x140009ad5  mov     [rdi+8], rax
0x140009ad9  mov     [rsp+4B0h+var_470], 0
0x140009ae2  lea     rcx, [rsp+4B0h+var_470]
0x140009ae7  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x140009aec  nop
0x140009aed  mov     [rsp+4B0h+var_490], 0; void *
0x140009af6  mov     r9, rdi; void *
0x140009af9  mov     r8d, 2; int
0x140009aff  mov     rdx, rsi; struct SynchronizedObject *
0x140009b02  mov     rcx, [rsi+8]; this
0x140009b06  call    ?EnqueueEvent@Synchronizer@@AEAAXPEAVSynchronizedObject@@HPEAX11@Z; Synchronizer::EnqueueEvent(SynchronizedObject *,int,void *,void *,void *)
0x140009b0b  cmp     [rsp+4B0h+var_444], 1
0x140009b10  mov     rbx, [rsp+4B0h+var_468]
0x140009b15  mov     ecx, 3E8h
0x140009b1a  jnz     loc_1400099FE
0x140009b20  xor     eax, eax
0x140009b22  mov     rcx, [rbp+3B0h+var_50]
0x140009b29  xor     rcx, rsp; StackCookie
0x140009b2c  call    __security_check_cookie
0x140009b31  add     rsp, 478h
0x140009b38  pop     r15
0x140009b3a  pop     r14
0x140009b3c  pop     r13
0x140009b3e  pop     r12
0x140009b40  pop     rdi
0x140009b41  pop     rsi
0x140009b42  pop     rbx
0x140009b43  pop     rbp
0x140009b44  retn
```
