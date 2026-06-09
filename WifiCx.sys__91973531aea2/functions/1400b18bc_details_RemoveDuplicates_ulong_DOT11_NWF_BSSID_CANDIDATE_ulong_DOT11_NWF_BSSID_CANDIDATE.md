# details::RemoveDuplicates(ulong,DOT11_NWF_BSSID_CANDIDATE *,ulong &,DOT11_NWF_BSSID_CANDIDATE *)

- ea: `0x1400b18bc`
- end: `0x1400b19ac`
- name: `?RemoveDuplicates@details@@YAXKPEAUDOT11_NWF_BSSID_CANDIDATE@@AEAK0@Z`
- size: `240`
- prototype: `void(unsigned int, struct DOT11_NWF_BSSID_CANDIDATE *, unsigned int *, struct DOT11_NWF_BSSID_CANDIDATE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400a19c0`

## callees

- `0x14006b8ac`
- `0x1400b18bc`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400b1916`
- `ntoskrnl!RtlCompareMemory` at `0x1400b1916`

## pseudocode

```c
void __fastcall details::RemoveDuplicates(
        unsigned int a1,
        struct DOT11_NWF_BSSID_CANDIDATE *a2,
        unsigned int *a3,
        struct DOT11_NWF_BSSID_CANDIDATE *a4)
{
  unsigned int v4; // r12d
  struct DOT11_NWF_BSSID_CANDIDATE *v7; // rbp
  struct DOT11_NWF_BSSID_CANDIDATE *i; // rbx
  struct DOT11_NWF_BSSID_CANDIDATE *v9; // rdi
  struct DOT11_NWF_BSSID_CANDIDATE *v10; // rsi
  unsigned int v11; // ecx

  v4 = *a3;
  v7 = (struct DOT11_NWF_BSSID_CANDIDATE *)((char *)a2 + 16 * a1);
  *a3 = 0;
  for ( i = a2; i != v7; i = (struct DOT11_NWF_BSSID_CANDIDATE *)((char *)i + 16) )
  {
    if ( *a3 >= v4 )
    {
LABEL_8:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(a2) = 5;
        WPP_RECORDER_SF__MAC_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          (_DWORD)a3,
          30,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          (__int64)i);
      }
    }
    else
    {
      v9 = a4;
      v10 = (struct DOT11_NWF_BSSID_CANDIDATE *)((char *)a4 + 16 * *a3);
      while ( v9 != v10 )
      {
        if ( RtlCompareMemory(i, v9, 6u) == 6 )
          goto LABEL_8;
        v9 = (struct DOT11_NWF_BSSID_CANDIDATE *)((char *)v9 + 16);
      }
      v11 = *a3;
      *((_OWORD *)a4 + *a3) = *(_OWORD *)i;
      *a3 = v11 + 1;
    }
  }
}

```

## disassembly

```asm
0x1400b18bc  push    rbx
0x1400b18be  push    rbp
0x1400b18bf  push    rsi
0x1400b18c0  push    rdi
0x1400b18c1  push    r12
0x1400b18c3  push    r13
0x1400b18c5  push    r14
0x1400b18c7  push    r15
0x1400b18c9  sub     rsp, 38h
0x1400b18cd  mov     r12d, [r8]
0x1400b18d0  xor     r13d, r13d
0x1400b18d3  mov     ebp, ecx
0x1400b18d5  mov     r15, r9
0x1400b18d8  shl     rbp, 4
0x1400b18dc  mov     r14, r8
0x1400b18df  add     rbp, rdx
0x1400b18e2  mov     [r8], r13d
0x1400b18e5  mov     rbx, rdx
0x1400b18e8  cmp     rdx, rbp
0x1400b18eb  jz      loc_1400B199A
0x1400b18f1  mov     eax, [r14]
0x1400b18f4  cmp     eax, r12d
0x1400b18f7  jnb     short loc_1400B1947
0x1400b18f9  mov     esi, eax
0x1400b18fb  mov     rdi, r15
0x1400b18fe  shl     rsi, 4
0x1400b1902  add     rsi, r15
0x1400b1905  cmp     rdi, rsi
0x1400b1908  jz      short loc_1400B192E
0x1400b190a  mov     r8d, 6; Length
0x1400b1910  mov     rdx, rdi; Source2
0x1400b1913  mov     rcx, rbx; Source1
0x1400b1916  call    cs:__imp_RtlCompareMemory
0x1400b191d  nop     dword ptr [rax+rax+00h]
0x1400b1922  cmp     rax, 6
0x1400b1926  jz      short loc_1400B1947
0x1400b1928  add     rdi, 10h
0x1400b192c  jmp     short loc_1400B1905
0x1400b192e  mov     ecx, [r14]
0x1400b1931  movups  xmm0, xmmword ptr [rbx]
0x1400b1934  mov     eax, ecx
0x1400b1936  add     rax, rax
0x1400b1939  movdqu  xmmword ptr [r15+rax*8], xmm0
0x1400b193f  lea     eax, [rcx+1]
0x1400b1942  mov     [r14], eax
0x1400b1945  jmp     short loc_1400B198D
0x1400b1947  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b194e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b1955  jz      short loc_1400B198D
0x1400b1957  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b195e  cmp     byte ptr [rcx+29h], 5
0x1400b1962  jnb     short loc_1400B196B
0x1400b1964  cmp     [rcx+48h], r13w
0x1400b1969  jz      short loc_1400B198D
0x1400b196b  mov     rcx, [rcx+40h]
0x1400b196f  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b1976  mov     r9d, 1Eh
0x1400b197c  mov     [rsp+78h+var_50], rbx
0x1400b1981  mov     dl, 5
0x1400b1983  mov     [rsp+78h+var_58], rax
0x1400b1988  call    WPP_RECORDER_SF__MAC_
0x1400b198d  add     rbx, 10h
0x1400b1991  cmp     rbx, rbp
0x1400b1994  jnz     loc_1400B18F1
0x1400b199a  add     rsp, 38h
0x1400b199e  pop     r15
0x1400b19a0  pop     r14
0x1400b19a2  pop     r13
0x1400b19a4  pop     r12
0x1400b19a6  pop     rdi
0x1400b19a7  pop     rsi
0x1400b19a8  pop     rbp
0x1400b19a9  pop     rbx
0x1400b19aa  retn
```
