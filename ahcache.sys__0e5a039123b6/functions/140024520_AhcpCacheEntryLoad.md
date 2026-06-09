# AhcpCacheEntryLoad

- ea: `0x140024520`
- end: `0x1400246f8`
- name: `AhcpCacheEntryLoad`
- size: `472`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140004553`
- `0x140007b40`
- `0x140024520`
- `0x14003e364`
- `0x140054bc0`
- `0x140055270`

## string_xrefs

- `0x1400246b8`: `Failed to read file time [%x]`
- `0x140024603`: `AhcpCacheEntryLoad`
- `0x1400246c4`: `AhcpCacheEntryLoad`
- `0x14002469c`: `Failed to read custom data size [%x]`
- `0x140024680`: `Failed to read custom data [%x]`

## pseudocode

```c
__int64 __fastcall AhcpCacheEntryLoad(_QWORD *a1, _QWORD *a2)
{
  int v4; // ebx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rcx
  __int64 v7; // rbx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rax
  unsigned int v12; // eax
  void *Pool2_0; // rax
  size_t v14; // rbx
  size_t v15; // rdx
  size_t v16; // rcx
  size_t v17; // rax
  __int64 v18; // r8
  const char *v19; // r9
  int v21; // [rsp+20h] [rbp-18h]

  v4 = AhcpCacheEntryAlloc();
  if ( v4 < 0 )
    goto LABEL_30;
  v5 = a2[1];
  v6 = a2[4];
  if ( v6 > v5 || v6 + 8 < v6 || v6 + 8 > v5 )
  {
    v4 = -1073741811;
LABEL_28:
    v18 = 1645;
    v19 = "Failed to read file time [%x]";
    goto LABEL_29;
  }
  v7 = *a1;
  *(_QWORD *)(*a1 + 8LL) = *(_QWORD *)(v6 + a2[5]);
  v8 = a2[4];
  v9 = v8 + 8;
  if ( v8 + 8 < v8 )
  {
    a2[4] = -1;
    v4 = -1073741675;
    goto LABEL_28;
  }
  a2[4] = v9;
  v10 = a2[1];
  if ( v9 > v10 || v9 + 4 < v9 || v9 + 4 > v10 )
  {
    v4 = -1073741811;
LABEL_26:
    v18 = 1651;
    v19 = "Failed to read custom data size [%x]";
    goto LABEL_29;
  }
  *(_DWORD *)(v7 + 16) = *(_DWORD *)(v9 + a2[5]);
  v11 = a2[4];
  if ( v11 + 4 < v11 )
  {
    a2[4] = -1;
    v4 = -1073741675;
    goto LABEL_26;
  }
  a2[4] = v11 + 4;
  v12 = *(_DWORD *)(v7 + 16);
  if ( v12 )
  {
    Pool2_0 = (void *)ExAllocatePool2_0(256, v12, 1953517633);
    *(_QWORD *)(v7 + 24) = Pool2_0;
    if ( !Pool2_0 )
    {
      AslLogCallPrintf(1, "AhcpCacheEntryLoad", 1658, "Failed to allocate memory for custom data");
      v4 = -1073741801;
LABEL_30:
      AhcpCacheEntryFree(*a1);
      *a1 = 0;
      return (unsigned int)v4;
    }
    v14 = *(unsigned int *)(v7 + 16);
    if ( v14 )
    {
      v15 = a2[1];
      v16 = a2[4];
      if ( v16 > v15 || v16 + v14 < v16 || v16 + v14 > v15 )
      {
        v4 = -1073741811;
      }
      else
      {
        memmove(Pool2_0, (const void *)(v16 + a2[5]), v14);
        v17 = a2[4];
        if ( v14 + v17 >= v17 )
        {
          a2[4] = v14 + v17;
          return 0;
        }
        a2[4] = -1;
        v4 = -1073741675;
      }
      v18 = 1666;
      v19 = "Failed to read custom data [%x]";
LABEL_29:
      v21 = v4;
      AslLogCallPrintf(1, "AhcpCacheEntryLoad", v18, v19, v21);
      goto LABEL_30;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140024520  mov     [rsp+arg_0], rbx
0x140024525  mov     [rsp+arg_8], rsi
0x14002452a  push    rdi
0x14002452b  sub     rsp, 30h
0x14002452f  mov     rdi, rdx
0x140024532  mov     rsi, rcx
0x140024535  call    AhcpCacheEntryAlloc
0x14002453a  mov     ebx, eax
0x14002453c  test    eax, eax
0x14002453e  js      loc_1400246D6
0x140024544  mov     rax, [rdi+8]
0x140024548  mov     rcx, [rdi+20h]
0x14002454c  cmp     rcx, rax
0x14002454f  jbe     short loc_14002455B
0x140024551  mov     ebx, 0C000000Dh
0x140024556  jmp     loc_1400246B2
0x14002455b  lea     rdx, [rcx+8]
0x14002455f  cmp     rdx, rcx
0x140024562  jb      short loc_140024551
0x140024564  cmp     rdx, rax
0x140024567  ja      short loc_140024551
0x140024569  mov     rax, [rdi+28h]
0x14002456d  mov     rbx, [rsi]
0x140024570  mov     rcx, [rcx+rax]
0x140024574  mov     [rbx+8], rcx
0x140024578  mov     rax, [rdi+20h]
0x14002457c  lea     rcx, [rax+8]
0x140024580  cmp     rcx, rax
0x140024583  jb      loc_1400246A5
0x140024589  mov     [rdi+20h], rcx
0x14002458d  mov     rax, [rdi+8]
0x140024591  cmp     rcx, rax
0x140024594  jbe     short loc_1400245A0
0x140024596  mov     ebx, 0C000000Dh
0x14002459b  jmp     loc_140024696
0x1400245a0  lea     rdx, [rcx+4]
0x1400245a4  cmp     rdx, rcx
0x1400245a7  jb      short loc_140024596
0x1400245a9  cmp     rdx, rax
0x1400245ac  ja      short loc_140024596
0x1400245ae  mov     rax, [rdi+28h]
0x1400245b2  mov     ecx, [rcx+rax]
0x1400245b5  mov     [rbx+10h], ecx
0x1400245b8  mov     rax, [rdi+20h]
0x1400245bc  lea     rcx, [rax+4]
0x1400245c0  cmp     rcx, rax
0x1400245c3  jb      loc_140024689
0x1400245c9  mov     [rdi+20h], rcx
0x1400245cd  mov     eax, [rbx+10h]
0x1400245d0  test    eax, eax
0x1400245d2  jz      loc_140024669
0x1400245d8  mov     edx, eax
0x1400245da  mov     ecx, 100h
0x1400245df  mov     r8d, 74705041h
0x1400245e5  call    ExAllocatePool2_0
0x1400245ea  mov     [rbx+18h], rax
0x1400245ee  mov     r9, rax
0x1400245f1  test    rax, rax
0x1400245f4  jnz     short loc_14002461C
0x1400245f6  lea     r9, aFailedToAlloca_1; "Failed to allocate memory for custom da"...
0x1400245fd  mov     r8d, 67Ah
0x140024603  lea     rdx, aAhcpcacheentry_7; "AhcpCacheEntryLoad"
0x14002460a  lea     ecx, [rax+1]
0x14002460d  call    AslLogCallPrintf
0x140024612  mov     ebx, 0C0000017h
0x140024617  jmp     loc_1400246D6
0x14002461c  mov     ebx, [rbx+10h]
0x14002461f  test    rbx, rbx
0x140024622  jz      short loc_140024669
0x140024624  mov     rdx, [rdi+8]
0x140024628  mov     rcx, [rdi+20h]
0x14002462c  cmp     rcx, rdx
0x14002462f  jbe     short loc_140024638
0x140024631  mov     ebx, 0C000000Dh
0x140024636  jmp     short loc_14002467A
0x140024638  lea     rax, [rcx+rbx]
0x14002463c  cmp     rax, rcx
0x14002463f  jb      short loc_140024631
0x140024641  cmp     rax, rdx
0x140024644  ja      short loc_140024631
0x140024646  mov     rdx, [rdi+28h]
0x14002464a  mov     r8, rbx; Size
0x14002464d  add     rdx, rcx; Src
0x140024650  mov     rcx, r9; void *
0x140024653  call    memmove
0x140024658  mov     rax, [rdi+20h]
0x14002465c  lea     rcx, [rbx+rax]
0x140024660  cmp     rcx, rax
0x140024663  jb      short loc_14002466D
0x140024665  mov     [rdi+20h], rcx
0x140024669  xor     ebx, ebx
0x14002466b  jmp     short loc_1400246E5
0x14002466d  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x140024675  mov     ebx, 0C0000095h
0x14002467a  mov     r8d, 682h
0x140024680  lea     r9, aFailedToReadCu; "Failed to read custom data [%x]"
0x140024687  jmp     short loc_1400246BF
0x140024689  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x140024691  mov     ebx, 0C0000095h
0x140024696  mov     r8d, 673h
0x14002469c  lea     r9, aFailedToReadCu_0; "Failed to read custom data size [%x]"
0x1400246a3  jmp     short loc_1400246BF
0x1400246a5  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x1400246ad  mov     ebx, 0C0000095h
0x1400246b2  mov     r8d, 66Dh
0x1400246b8  lea     r9, aFailedToReadFi_0; "Failed to read file time [%x]"
0x1400246bf  mov     ecx, 1
0x1400246c4  lea     rdx, aAhcpcacheentry_7; "AhcpCacheEntryLoad"
0x1400246cb  mov     eax, ebx
0x1400246cd  mov     [rsp+38h+var_18], ebx
0x1400246d1  call    AslLogCallPrintf
0x1400246d6  mov     rcx, [rsi]
0x1400246d9  call    AhcpCacheEntryFree
0x1400246de  mov     qword ptr [rsi], 0
0x1400246e5  mov     rsi, [rsp+38h+arg_8]
0x1400246ea  mov     eax, ebx
0x1400246ec  mov     rbx, [rsp+38h+arg_0]
0x1400246f1  add     rsp, 30h
0x1400246f5  pop     rdi
0x1400246f6  retn
```
