# Streaming::Context::StreamingBitmapBuilder::QueryAllocationRanges(appv::shared::kernel::auto_ptr<Streaming::Context::StreamingBitMap,appv::shared::kernel::AllocDelete<Streaming::Context::StreamingBitMap>> &,__int64,_FILE_ALLOCATED_RANGE_BUFFER const &,_FILE_ALLOCATED_RANGE_BUFFER * const,ulong,ulong &)

- ea: `0x14000af6c`
- end: `0x14000b0b3`
- name: `?QueryAllocationRanges@StreamingBitmapBuilder@Context@Streaming@@SAJAEAV?$auto_ptr@VStreamingBitMap@Context@Streaming@@U?$AllocDelete@VStreamingBitMap@Context@Streaming@@@kernel@shared@appv@@@kernel@shared@appv@@_JAEBU_FILE_ALLOCATED_RANGE_BUFFER@@QEAU8@KAEAK@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140008dc4`

## callees

- `0x14000af6c`
- `0x14000fab8`

## pseudocode

```c
__int64 __fastcall Streaming::Context::StreamingBitmapBuilder::QueryAllocationRanges(
        PRTL_BITMAP *a1,
        __int64 a2,
        union _LARGE_INTEGER *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6)
{
  union _LARGE_INTEGER v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rdi
  unsigned int v11; // ecx
  unsigned int v12; // r14d
  union _LARGE_INTEGER v13; // rdx

  if ( !a5 || !a4 )
    return 3221225485LL;
  v8 = *a3;
  v9 = a3->QuadPart % 0x10000;
  if ( v9 )
    v8.QuadPart = a3->QuadPart - v9;
  v10 = v8.QuadPart + a3[1].QuadPart - a3->QuadPart;
  if ( v10 % 0x10000 )
  {
    if ( v10 + v8.QuadPart != a2 )
    {
      v10 = v10 - v10 % 0x10000 + 0x10000;
      if ( a2 - v8.QuadPart < v10 )
        v10 = a2 - v8.QuadPart;
    }
  }
  *a6 = 0;
  v11 = 0;
  while ( 1 )
  {
    *(union _LARGE_INTEGER *)(a4 + 16LL * v11) = v8;
    v12 = 0;
    *(_QWORD *)(a4 + 16LL * *a6 + 8) = 0;
    do
    {
      *(_QWORD *)(16LL * *a6 + a4 + 8) += v12;
      if ( !v10 )
        break;
      v12 = 0x10000;
      if ( v10 <= 0x10000 )
        v12 = v10;
      v13 = v8;
      v10 -= v12;
      v8.QuadPart += v12;
    }
    while ( Streaming::Context::StreamingBitMap::IsSafeToRead(*a1, v13, v12) );
    v11 = *a6;
    if ( *(_QWORD *)(a4 + 16LL * *a6 + 8) )
      *a6 = ++v11;
    if ( !v10 )
      break;
    if ( v11 >= a5 )
      return 261;
  }
  return 0;
}

```

## disassembly

```asm
0x14000af6c  push    rbx
0x14000af6e  push    rbp
0x14000af6f  push    rsi
0x14000af70  push    rdi
0x14000af71  push    r12
0x14000af73  push    r14
0x14000af75  sub     rsp, 28h
0x14000af79  cmp     [rsp+58h+arg_20], 0
0x14000af81  mov     rbp, r9
0x14000af84  mov     r11, rdx
0x14000af87  mov     r12, rcx
0x14000af8a  jz      loc_14000B0A0
0x14000af90  test    r9, r9
0x14000af93  jz      loc_14000B0A0
0x14000af99  mov     r10, [r8]
0x14000af9c  mov     r9d, 0FFFFh
0x14000afa2  mov     rdi, [r8+8]
0x14000afa6  mov     rax, r10
0x14000afa9  cqo
0x14000afab  mov     rcx, r10
0x14000afae  and     rdx, r9
0x14000afb1  mov     rbx, r10
0x14000afb4  add     rax, rdx
0x14000afb7  and     rax, r9
0x14000afba  sub     rax, rdx
0x14000afbd  sub     rcx, rax
0x14000afc0  test    rax, rax
0x14000afc3  cmovnz  rbx, rcx
0x14000afc7  sub     rdi, r10
0x14000afca  add     rdi, rbx
0x14000afcd  mov     rax, rdi
0x14000afd0  cqo
0x14000afd2  and     rdx, r9
0x14000afd5  lea     rcx, [rdx+rax]
0x14000afd9  and     rcx, r9
0x14000afdc  sub     rcx, rdx
0x14000afdf  jz      short loc_14000AFFE
0x14000afe1  lea     rax, [rdi+rbx]
0x14000afe5  cmp     rax, r11
0x14000afe8  jz      short loc_14000AFFE
0x14000afea  sub     rdi, rcx
0x14000afed  sub     r11, rbx
0x14000aff0  add     rdi, 10000h
0x14000aff7  cmp     r11, rdi
0x14000affa  cmovl   rdi, r11
0x14000affe  cmp     [rsp+58h+arg_20], 0
0x14000b006  mov     rsi, [rsp+58h+arg_28]
0x14000b00e  mov     dword ptr [rsi], 0
0x14000b014  jbe     short loc_14000B095
0x14000b016  xor     ecx, ecx
0x14000b018  mov     eax, ecx
0x14000b01a  add     rax, rax
0x14000b01d  mov     [rbp+rax*8+0], rbx
0x14000b022  mov     eax, [rsi]
0x14000b024  add     rax, rax
0x14000b027  xor     r14d, r14d
0x14000b02a  mov     qword ptr [rbp+rax*8+8], 0
0x14000b033  mov     ecx, [rsi]
0x14000b035  shl     rcx, 4
0x14000b039  mov     eax, r14d
0x14000b03c  add     [rcx+rbp+8], rax
0x14000b041  test    rdi, rdi
0x14000b044  jz      short loc_14000B074
0x14000b046  mov     r14d, 10000h
0x14000b04c  cmp     rdi, 10000h
0x14000b053  jg      short loc_14000B058
0x14000b055  mov     r14d, edi
0x14000b058  mov     rcx, [r12]; BitMapHeader
0x14000b05c  mov     rdx, rbx; union _LARGE_INTEGER
0x14000b05f  mov     eax, r14d
0x14000b062  mov     r8d, r14d; unsigned int
0x14000b065  sub     rdi, rax
0x14000b068  add     rbx, rax
0x14000b06b  call    ?IsSafeToRead@StreamingBitMap@Context@Streaming@@QEAAET_LARGE_INTEGER@@K@Z; Streaming::Context::StreamingBitMap::IsSafeToRead(_LARGE_INTEGER,ulong)
0x14000b070  test    al, al
0x14000b072  jnz     short loc_14000B033
0x14000b074  mov     ecx, [rsi]
0x14000b076  mov     eax, ecx
0x14000b078  add     rax, rax
0x14000b07b  cmp     qword ptr [rbp+rax*8+8], 0
0x14000b081  jz      short loc_14000B087
0x14000b083  inc     ecx
0x14000b085  mov     [rsi], ecx
0x14000b087  test    rdi, rdi
0x14000b08a  jz      short loc_14000B09C
0x14000b08c  cmp     ecx, [rsp+58h+arg_20]
0x14000b093  jb      short loc_14000B018
0x14000b095  mov     eax, 105h
0x14000b09a  jmp     short loc_14000B0A5
0x14000b09c  xor     eax, eax
0x14000b09e  jmp     short loc_14000B0A5
0x14000b0a0  mov     eax, 0C000000Dh
0x14000b0a5  add     rsp, 28h
0x14000b0a9  pop     r14
0x14000b0ab  pop     r12
0x14000b0ad  pop     rdi
0x14000b0ae  pop     rsi
0x14000b0af  pop     rbp
0x14000b0b0  pop     rbx
0x14000b0b1  retn
```
