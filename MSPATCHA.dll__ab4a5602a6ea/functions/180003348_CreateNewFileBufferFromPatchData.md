# CreateNewFileBufferFromPatchData

- ea: `0x180003348`
- end: `0x180003577`
- name: `CreateNewFileBufferFromPatchData`
- size: `559`
- prototype: `__int64 __fastcall(int, unsigned int, int, int, __int64, unsigned int, int, unsigned int, __int64, char *Src, int, __int64, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180001d10`
- `0x1800036e0`

## callees

- `0x180003348`
- `0x180004a9c`
- `0x180006d9c`
- `0x180006dd4`
- `0x180009061`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003550`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003550`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000353c`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000353c`

## pseudocode

```c
__int64 __fastcall CreateNewFileBufferFromPatchData(
        int a1,
        unsigned int a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        unsigned int a8,
        __int64 a9,
        char *Src,
        int a11,
        __int64 a12,
        unsigned int a13,
        __int64 a14)
{
  unsigned int v16; // r14d
  unsigned int v18; // r10d
  unsigned int i; // r8d
  __int64 result; // rax
  __int64 v21; // r15
  __int64 v22; // rcx
  DWORD v23; // esi
  __int64 v24; // r11
  unsigned int v25; // edi
  __int64 v26; // rbx
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rax
  __int64 v30; // r14
  size_t v31; // r8
  _QWORD *v32; // rcx
  _QWORD *v33; // rbx

  v16 = a2;
  if ( a13 )
  {
    i = a13;
  }
  else
  {
    v18 = a6 + ((a2 + 0x7FFF) & 0xFFFF8000);
    i = 0x20000;
    if ( v18 > 0x20000 )
    {
      for ( i = (a11 & 4) != 0 ? 0x2000000 : 0x800000; i >> 1 >= v18; i >>= 1 )
        ;
    }
  }
  result = CreateSubAllocator(i + 0x10000);
  v21 = result;
  if ( result )
  {
    v23 = ApplyRawLzxPatchToBuffer(a1, v16, a3, a4, a5, a6, a11, a13, a14);
    if ( v23 )
    {
      v25 = 1;
    }
    else
    {
      v25 = 1;
      if ( ~(unsigned int)Crc32(v22, a5, a6) == a7 )
      {
        v26 = 0;
        while ( (unsigned int)v26 < a8 )
        {
          v28 = v16;
          v29 = *(unsigned int *)(a9 + 12 * v26 + 8);
          v30 = 12 * v26;
          if ( v29 <= v28 )
          {
            v31 = *(unsigned int *)(v30 + a9 + 4);
            if ( v31 <= v28 - v29 )
            {
              memcpy_0((void *)(v29 + v24), Src, v31);
              v24 = a5;
            }
          }
          Src += *(unsigned int *)(v30 + a9 + 4);
          v26 = (unsigned int)(v26 + 1);
          v16 = a2;
        }
      }
      else
      {
        v23 = -1072807676;
      }
    }
    v32 = *(_QWORD **)(v21 + 8);
    do
    {
      v33 = (_QWORD *)*v32;
      VirtualFree(v32, 0, 0x8000u);
      v32 = v33;
    }
    while ( v33 );
    if ( v23 )
    {
      SetLastError(v23);
      return 0;
    }
    return v25;
  }
  return result;
}

```

## disassembly

```asm
0x180003348  mov     [rsp+arg_0], rbx
0x18000334d  mov     [rsp+arg_10], rsi
0x180003352  mov     [rsp+arg_8], edx
0x180003356  push    rdi
0x180003357  push    r12
0x180003359  push    r13
0x18000335b  push    r14
0x18000335d  push    r15
0x18000335f  sub     rsp, 90h
0x180003366  mov     esi, r9d
0x180003369  mov     r12, r8
0x18000336c  mov     r14d, edx
0x18000336f  mov     r13, rcx
0x180003372  mov     edi, [rsp+0B8h+arg_60]
0x180003379  mov     ebx, [rsp+0B8h+arg_28]
0x180003380  test    edi, edi
0x180003382  jnz     short loc_1800033CD
0x180003384  lea     r10d, [rdx+7FFFh]
0x18000338b  and     r10d, 0FFFF8000h
0x180003392  add     r10d, ebx
0x180003395  mov     r8d, 20000h
0x18000339b  cmp     r10d, r8d
0x18000339e  jbe     short loc_1800033D0
0x1800033a0  mov     eax, [rsp+0B8h+arg_50]
0x1800033a7  and     al, 4
0x1800033a9  neg     al
0x1800033ab  sbb     r8d, r8d
0x1800033ae  and     r8d, 1800000h
0x1800033b5  add     r8d, 800000h
0x1800033bc  jmp     short loc_1800033C1
0x1800033be  shr     r8d, 1
0x1800033c1  mov     eax, r8d
0x1800033c4  shr     eax, 1
0x1800033c6  cmp     eax, r10d
0x1800033c9  jnb     short loc_1800033BE
0x1800033cb  jmp     short loc_1800033D0
0x1800033cd  mov     r8d, edi
0x1800033d0  lea     ecx, [r8+10000h]
0x1800033d7  call    CreateSubAllocator
0x1800033dc  mov     r15, rax
0x1800033df  mov     [rsp+0B8h+arg_58], rax
0x1800033e7  test    rax, rax
0x1800033ea  jz      loc_18000355A
0x1800033f0  mov     [rsp+0B8h+var_48], ebx
0x1800033f4  mov     rax, [rsp+0B8h+arg_78]
0x1800033fc  mov     [rsp+0B8h+var_58], rax
0x180003401  mov     rax, [rsp+0B8h+arg_70]
0x180003409  mov     [rsp+0B8h+var_60], rax
0x18000340e  mov     [rsp+0B8h+var_68], r15
0x180003413  mov     rax, [rsp+0B8h+arg_68]
0x18000341b  mov     [rsp+0B8h+var_78], rax
0x180003420  mov     [rsp+0B8h+var_80], edi
0x180003424  mov     eax, [rsp+0B8h+arg_50]
0x18000342b  mov     [rsp+0B8h+var_88], eax
0x18000342f  mov     [rsp+0B8h+var_90], ebx
0x180003433  mov     rax, [rsp+0B8h+arg_20]
0x18000343b  mov     [rsp+0B8h+var_98], rax
0x180003440  mov     r9d, esi
0x180003443  mov     r8, r12
0x180003446  mov     edx, r14d
0x180003449  mov     rcx, r13
0x18000344c  call    ApplyRawLzxPatchToBuffer
0x180003451  mov     esi, eax
0x180003453  mov     [rsp+0B8h+var_38], eax
0x18000345a  test    eax, eax
0x18000345c  jnz     loc_180003510
0x180003462  mov     r8d, ebx
0x180003465  mov     r11, [rsp+0B8h+arg_20]
0x18000346d  mov     rdx, r11
0x180003470  call    Crc32
0x180003475  not     eax
0x180003477  lea     edi, [rsi+1]
0x18000347a  cmp     eax, [rsp+0B8h+arg_30]
0x180003481  jnz     short loc_180003502
0x180003483  xor     ebx, ebx
0x180003485  mov     [rsp+0B8h+var_34], ebx
0x18000348c  mov     r12, [rsp+0B8h+Src]
0x180003494  mov     r13, [rsp+0B8h+arg_40]
0x18000349c  cmp     ebx, [rsp+0B8h+arg_38]
0x1800034a3  jnb     short loc_180003515
0x1800034a5  mov     edx, r14d
0x1800034a8  lea     rcx, [rbx+rbx*2]
0x1800034ac  mov     eax, [r13+rcx*4+8]
0x1800034b1  lea     r14, ds:0[rcx*4]
0x1800034b9  cmp     rax, rdx
0x1800034bc  ja      short loc_1800034DF
0x1800034be  mov     r8d, [r14+r13+4]; Size
0x1800034c3  sub     rdx, rax
0x1800034c6  cmp     r8, rdx
0x1800034c9  ja      short loc_1800034DF
0x1800034cb  lea     rcx, [rax+r11]; void *
0x1800034cf  mov     rdx, r12; Src
0x1800034d2  call    memcpy_0
0x1800034d7  mov     r11, [rsp+0B8h+arg_20]
0x1800034df  mov     eax, [r14+r13+4]
0x1800034e4  add     r12, rax
0x1800034e7  mov     [rsp+0B8h+Src], r12
0x1800034ef  add     ebx, edi
0x1800034f1  mov     [rsp+0B8h+var_34], ebx
0x1800034f8  mov     r14d, [rsp+0B8h+arg_8]
0x180003500  jmp     short loc_18000349C
0x180003502  mov     esi, 0C00E4104h
0x180003507  mov     [rsp+0B8h+var_38], esi
0x18000350e  jmp     short loc_180003515
0x180003510  mov     edi, 1
0x180003515  jmp     short loc_18000352D
0x180003517  mov     esi, eax
0x180003519  mov     [rsp+0B8h+var_38], eax
0x180003520  mov     edi, 1
0x180003525  mov     r15, [rsp+0B8h+arg_58]
0x18000352d  mov     rcx, [r15+8]; lpAddress
0x180003531  mov     rbx, [rcx]
0x180003534  xor     edx, edx; dwSize
0x180003536  mov     r8d, 8000h; dwFreeType
0x18000353c  call    cs:__imp_VirtualFree
0x180003542  mov     rcx, rbx
0x180003545  test    rbx, rbx
0x180003548  jnz     short loc_180003531
0x18000354a  test    esi, esi
0x18000354c  jz      short loc_180003558
0x18000354e  mov     ecx, esi; dwErrCode
0x180003550  call    cs:__imp_SetLastError
0x180003556  xor     edi, edi
0x180003558  mov     eax, edi
0x18000355a  lea     r11, [rsp+0B8h+var_28]
0x180003562  mov     rbx, [r11+30h]
0x180003566  mov     rsi, [r11+40h]
0x18000356a  mov     rsp, r11
0x18000356d  pop     r15
0x18000356f  pop     r14
0x180003571  pop     r13
0x180003573  pop     r12
0x180003575  pop     rdi
0x180003576  retn
```
