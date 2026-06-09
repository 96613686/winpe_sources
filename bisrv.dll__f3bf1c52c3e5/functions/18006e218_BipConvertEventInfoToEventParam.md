# BipConvertEventInfoToEventParam

- ea: `0x18006e218`
- end: `0x18006e3bd`
- name: `BipConvertEventInfoToEventParam`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004786c`

## callees

- `0x180031f20`
- `0x18006e218`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18006e361`
- `ntdll!RtlFreeHeap` at `0x18006e398`
- `ntdll!RtlFreeHeap` at `0x18006e361`
- `ntdll!RtlFreeHeap` at `0x18006e398`
- `ntdll!RtlAllocateHeap` at `0x18006e32d`
- `ntdll!RtlAllocateHeap` at `0x18006e32d`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18006e272`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18006e272`
- `EventAggregation!BriIsBrokerRegistered` at `0x18006e2ad`
- `EventAggregation!BriIsBrokerRegistered` at `0x18006e2ad`

## pseudocode

```c
__int64 __fastcall BipConvertEventInfoToEventParam(GUID *a1, PVOID *a2, _WORD *a3, _BYTE *a4)
{
  GUID v7; // xmm0
  GUID v9; // xmm0
  void *v11; // rdi
  int v12; // ebx
  PVOID Heap; // rax
  int v14; // eax
  GUID v15; // xmm0
  unsigned __int16 v16; // [rsp+20h] [rbp-58h] BYREF
  __int128 v17; // [rsp+28h] [rbp-50h] BYREF
  __int128 v18; // [rsp+38h] [rbp-40h] BYREF
  __int128 v19; // [rsp+48h] [rbp-30h]
  GUID Source1; // [rsp+58h] [rbp-20h] BYREF

  v18 = 0;
  v19 = 0;
  *(_QWORD *)((char *)&v17 + 2) = 0;
  v7 = *a1;
  *(_QWORD *)&v17 = 0;
  Source1 = v7;
  if ( RtlCompareMemory(&Source1, &GUID_SYSTEM_EVENTS_BROKER, 0x10u) == 16 )
  {
    switch ( *((_DWORD *)*a2 + 2) )
    {
      case 0x1D:
        goto LABEL_7;
      case 0x1E:
        v9 = GUID_GEOLOCATION_BROKER;
        goto LABEL_8;
      case 0x26:
      case 0x27:
      case 0x29:
LABEL_7:
        v9 = GUID_NFC_BROKER;
LABEL_8:
        Source1 = v9;
        break;
    }
  }
  if ( !(unsigned __int8)BriIsBrokerRegistered(&Source1) )
  {
    *a4 = 0;
    return 0;
  }
  v11 = 0;
  DWORD2(v18) = 4;
  v16 = 0;
  *(_QWORD *)&v18 = L"EventInformation";
  LOWORD(v19) = *a3;
  *((_QWORD *)&v19 + 1) = *a2;
  *((_QWORD *)&v17 + 1) = &v18;
  LOWORD(v17) = 1;
  v12 = BrpEncodeBrokeredEvent_V1(&v17, 0, 0, &v16);
  if ( v12 != -1073741789 )
    goto LABEL_15;
  Heap = RtlAllocateHeap(BipHeap, 0, v16);
  v11 = Heap;
  if ( Heap )
  {
    v12 = BrpEncodeBrokeredEvent_V1(&v17, v16, Heap, &v16);
LABEL_15:
    if ( v12 < 0 )
    {
      if ( v11 )
        RtlFreeHeap(BipHeap, 0, v11);
    }
    else
    {
      RtlFreeHeap(BipHeap, 0, *a2);
      v14 = v16;
      v15 = Source1;
      *a2 = v11;
      *(_DWORD *)a3 = v14;
      *a4 = 1;
      *a1 = v15;
    }
    return (unsigned int)v12;
  }
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x18006e218  push    rbp
0x18006e21a  push    rbx
0x18006e21b  push    rsi
0x18006e21c  push    rdi
0x18006e21d  push    r12
0x18006e21f  push    r13
0x18006e221  push    r14
0x18006e223  push    r15
0x18006e225  mov     rbp, rsp
0x18006e228  sub     rsp, 78h
0x18006e22c  mov     rax, cs:__security_cookie
0x18006e233  xor     rax, rsp
0x18006e236  mov     [rbp+var_10], rax
0x18006e23a  xorps   xmm0, xmm0
0x18006e23d  xor     eax, eax
0x18006e23f  movups  [rbp+var_40], xmm0
0x18006e243  mov     r15, r8
0x18006e246  mov     rsi, rdx
0x18006e249  movups  [rbp+var_30], xmm0
0x18006e24d  mov     r12, rcx
0x18006e250  mov     [rbp+var_4E], rax
0x18006e254  movups  xmm0, xmmword ptr [rcx]
0x18006e257  lea     r8d, [rax+10h]; Length
0x18006e25b  mov     [rbp-50h], rax
0x18006e25f  lea     rdx, GUID_SYSTEM_EVENTS_BROKER; Source2
0x18006e266  mov     r14, r9
0x18006e269  lea     rcx, [rbp+Source1]; Source1
0x18006e26d  movdqu  [rbp+Source1], xmm0
0x18006e272  call    cs:__imp_RtlCompareMemory
0x18006e278  cmp     rax, 10h
0x18006e27c  jnz     short loc_18006E2A9
0x18006e27e  mov     rcx, [rsi]
0x18006e281  mov     edx, [rcx+8]
0x18006e284  sub     edx, 1Dh
0x18006e287  jz      short loc_18006E29D
0x18006e289  sub     edx, 1
0x18006e28c  jz      short loc_18006E2C1
0x18006e28e  sub     edx, 8
0x18006e291  jz      short loc_18006E29D
0x18006e293  sub     edx, 1
0x18006e296  jz      short loc_18006E29D
0x18006e298  cmp     edx, 2
0x18006e29b  jnz     short loc_18006E2A9
0x18006e29d  movups  xmm0, xmmword ptr cs:GUID_NFC_BROKER.Data1
0x18006e2a4  movdqu  [rbp+Source1], xmm0
0x18006e2a9  lea     rcx, [rbp+Source1]
0x18006e2ad  call    cs:__imp_BriIsBrokerRegistered
0x18006e2b3  test    al, al
0x18006e2b5  jnz     short loc_18006E2CA
0x18006e2b7  mov     [r14], al
0x18006e2ba  xor     eax, eax
0x18006e2bc  jmp     loc_18006E3A0
0x18006e2c1  movups  xmm0, xmmword ptr cs:GUID_GEOLOCATION_BROKER.Data1
0x18006e2c8  jmp     short loc_18006E2A4
0x18006e2ca  xor     edi, edi
0x18006e2cc  mov     dword ptr [rbp+var_40+8], 4
0x18006e2d3  xor     eax, eax
0x18006e2d5  mov     [rbp+var_58], ax
0x18006e2d9  lea     rax, aEventinformati; "EventInformation"
0x18006e2e0  mov     qword ptr [rbp+var_40], rax
0x18006e2e4  movzx   eax, word ptr [r15]
0x18006e2e8  lea     r13d, [rdi+1]
0x18006e2ec  mov     word ptr [rbp+var_30], ax
0x18006e2f0  mov     rax, [rsi]
0x18006e2f3  mov     qword ptr [rbp+var_30+8], rax
0x18006e2f7  lea     rax, [rbp+var_40]
0x18006e2fb  mov     [rbp+var_4E+6], rax
0x18006e2ff  mov     [rbp+var_50], r13w
0x18006e304  xor     edx, edx
0x18006e306  lea     r9, [rbp+var_58]
0x18006e30a  xor     r8d, r8d
0x18006e30d  lea     rcx, [rbp+var_50]
0x18006e311  call    BrpEncodeBrokeredEvent_V1
0x18006e316  mov     ebx, eax
0x18006e318  cmp     eax, 0C0000023h
0x18006e31d  jnz     short loc_18006E351
0x18006e31f  movzx   r8d, [rbp+var_58]; Size
0x18006e324  xor     edx, edx; Flags
0x18006e326  mov     rcx, cs:BipHeap; HeapHandle
0x18006e32d  call    cs:__imp_RtlAllocateHeap
0x18006e333  mov     rdi, rax
0x18006e336  test    rax, rax
0x18006e339  jz      short loc_18006E380
0x18006e33b  movzx   edx, [rbp+var_58]
0x18006e33f  lea     r9, [rbp+var_58]
0x18006e343  mov     r8, rax
0x18006e346  lea     rcx, [rbp+var_50]
0x18006e34a  call    BrpEncodeBrokeredEvent_V1
0x18006e34f  mov     ebx, eax
0x18006e351  test    ebx, ebx
0x18006e353  js      short loc_18006E387
0x18006e355  mov     r8, [rsi]; P
0x18006e358  xor     edx, edx; Flags
0x18006e35a  mov     rcx, cs:BipHeap; HeapHandle
0x18006e361  call    cs:__imp_RtlFreeHeap
0x18006e367  movzx   eax, [rbp+var_58]
0x18006e36b  movups  xmm0, [rbp+Source1]
0x18006e36f  mov     [rsi], rdi
0x18006e372  mov     [r15], eax
0x18006e375  mov     [r14], r13b
0x18006e378  movdqu  xmmword ptr [r12], xmm0
0x18006e37e  jmp     short loc_18006E39E
0x18006e380  mov     ebx, 0C0000017h
0x18006e385  jmp     short loc_18006E39E
0x18006e387  test    rdi, rdi
0x18006e38a  jz      short loc_18006E39E
0x18006e38c  mov     rcx, cs:BipHeap; HeapHandle
0x18006e393  mov     r8, rdi; P
0x18006e396  xor     edx, edx; Flags
0x18006e398  call    cs:__imp_RtlFreeHeap
0x18006e39e  mov     eax, ebx
0x18006e3a0  mov     rcx, [rbp+var_10]
0x18006e3a4  xor     rcx, rsp; StackCookie
0x18006e3a7  call    __security_check_cookie
0x18006e3ac  add     rsp, 78h
0x18006e3b0  pop     r15
0x18006e3b2  pop     r14
0x18006e3b4  pop     r13
0x18006e3b6  pop     r12
0x18006e3b8  pop     rdi
0x18006e3b9  pop     rsi
0x18006e3ba  pop     rbx
0x18006e3bb  pop     rbp
0x18006e3bc  retn
```
