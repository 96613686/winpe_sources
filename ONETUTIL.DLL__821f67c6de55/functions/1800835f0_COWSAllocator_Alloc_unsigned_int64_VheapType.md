# COWSAllocator::Alloc(unsigned __int64,VheapType)

- ea: `0x1800835f0`
- end: `0x18008378b`
- name: `?Alloc@COWSAllocator@@SAPEAX_KW4VheapType@@@Z`
- size: `411`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180083f64`
- `0x180084d74`
- `0x18008536c`
- `0x180085cf0`
- `0x1800db0d0`

## callees

- `0x1800835f0`
- `0x180086194`
- `0x180086284`
- `0x1800c34b8`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x180083724`
- `KERNEL32!DebugBreak` at `0x180083724`
- `KERNEL32!TlsGetValue` at `0x18008362a`
- `KERNEL32!TlsGetValue` at `0x18008362a`
- `KERNEL32!GetCurrentThreadId` at `0x18008372f`
- `KERNEL32!GetCurrentThreadId` at `0x18008372f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800836b5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800836b5`

## pseudocode

```c
char *__fastcall COWSAllocator::Alloc(__int64 a1, int a2)
{
  __int64 *v2; // rbx
  char v3; // si
  unsigned __int64 v5; // rbp
  _QWORD *Value; // rax
  unsigned __int64 v7; // rdx
  __int64 v8; // rcx
  _DWORD *v9; // rax
  __int64 v10; // rcx
  _DWORD *v11; // rdi
  __int64 v12; // rcx
  int v13; // ecx
  int v14; // eax
  DWORD CurrentThreadId; // eax
  char *result; // rax
  int v17; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v3 = 0;
  v17 = 0;
  v5 = a1;
  if ( a2 )
  {
    if ( a2 == 2 )
      goto LABEL_5;
    if ( a2 != 3 )
      goto LABEL_11;
  }
  Value = TlsGetValue(dword_1802AF500);
  if ( !Value )
  {
LABEL_5:
    if ( qword_1802B0010 )
      v2 = *(__int64 **)qword_1802B0010;
    goto LABEL_11;
  }
  a1 = 0xFFFFFFFFLL;
  if ( Value != (_QWORD *)0xFFFFFFFFLL )
  {
    if ( a2 )
      v2 = (__int64 *)Value[2];
    else
      v2 = (__int64 *)Value[1];
  }
LABEL_11:
  if ( v5 > 0x40000000 )
    sub_1800C34B8(a1);
  v7 = (((v5 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 8) & 0xFFFFFFF8;
  if ( v2 )
  {
    if ( (v2[2] & 0x20) != 0 )
    {
      v3 = 1;
      v7 = (v7 + 47) & 0xFFFFFFF8;
    }
    v8 = *v2;
    v17 = v7;
    v9 = (_DWORD *)(*(__int64 (__fastcall **)(__int64, unsigned __int64, int *, _QWORD))(*(_QWORD *)v8 + 40LL))(
                     v8,
                     v7,
                     &v17,
                     0);
  }
  else
  {
    v9 = malloc((((v5 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 8) & 0xFFFFFFF8);
  }
  v11 = v9;
  if ( !v9 )
    sub_1800C34B8(v10);
  if ( v3 )
  {
    if ( *((char *)v2 + 16) < 0 )
      sub_180086194(v2);
    v12 = *(_QWORD *)qword_1802B0010;
    if ( *(_QWORD *)qword_1802B0010 && (__int64 *)v12 != v2 && *(char *)(v12 + 16) < 0 )
      sub_180086194(v12);
    v13 = *((_DWORD *)v2 + 3);
    if ( (v2[2] & 2) != 0 )
    {
      v14 = _InterlockedIncrement((volatile signed __int32 *)v2 + 2);
    }
    else
    {
      v14 = *((_DWORD *)v2 + 2) + 1;
      *((_DWORD *)v2 + 2) = v14;
    }
    if ( v13 && v13 == v14 )
      DebugBreak();
    *v11 = *((_DWORD *)v2 + 2);
    CurrentThreadId = GetCurrentThreadId();
    v11[4] = -1;
    v11[1] = CurrentThreadId;
    *((_QWORD *)v11 + 1) = "(unknown file)";
    *((_QWORD *)v11 + 3) = v5;
    v11[8] = v17;
    sub_180086284(v2, v17);
    v11 += 10;
  }
  result = (char *)(v11 + 2);
  *(_QWORD *)v11 = v2;
  return result;
}

```

## disassembly

```asm
0x1800835f0  mov     rax, rsp
0x1800835f3  mov     [rax+8], rbx
0x1800835f7  mov     [rax+18h], rbp
0x1800835fb  mov     [rax+20h], rsi
0x1800835ff  push    rdi
0x180083600  sub     rsp, 30h
0x180083604  xor     ebx, ebx
0x180083606  xor     sil, sil
0x180083609  and     [rax+10h], ebx
0x18008360c  mov     edi, edx
0x18008360e  mov     rbp, rcx
0x180083611  mov     r8d, edx
0x180083614  test    edx, edx
0x180083616  jz      short loc_180083624
0x180083618  sub     r8d, 2
0x18008361c  jz      short loc_180083635
0x18008361e  cmp     r8d, 1
0x180083622  jnz     short loc_18008365E
0x180083624  mov     ecx, cs:dword_1802AF500; dwTlsIndex
0x18008362a  call    cs:TlsGetValue
0x180083630  test    rax, rax
0x180083633  jnz     short loc_180083646
0x180083635  mov     rax, cs:qword_1802B0010
0x18008363c  test    rax, rax
0x18008363f  jz      short loc_18008365E
0x180083641  mov     rbx, [rax]
0x180083644  jmp     short loc_18008365E
0x180083646  mov     ecx, 0FFFFFFFFh
0x18008364b  cmp     rax, rcx
0x18008364e  jz      short loc_18008365E
0x180083650  test    edi, edi
0x180083652  jnz     short loc_18008365A
0x180083654  mov     rbx, [rax+8]
0x180083658  jmp     short loc_18008365E
0x18008365a  mov     rbx, [rax+10h]
0x18008365e  cmp     rbp, 40000000h
0x180083665  ja      loc_18008377F
0x18008366b  lea     rdx, [rbp+7]
0x18008366f  mov     eax, 0FFFFFFF8h
0x180083674  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180083678  add     rdx, 8
0x18008367c  and     rdx, rax
0x18008367f  test    rbx, rbx
0x180083682  jz      short loc_1800836B2
0x180083684  test    byte ptr [rbx+10h], 20h
0x180083688  jz      short loc_180083694
0x18008368a  add     rdx, 2Fh ; '/'
0x18008368e  mov     sil, 1
0x180083691  and     rdx, rax
0x180083694  mov     rcx, [rbx]
0x180083697  lea     r8, [rsp+38h+arg_8]
0x18008369c  mov     [rsp+38h+arg_8], edx
0x1800836a0  xor     r9d, r9d
0x1800836a3  mov     rax, [rcx]
0x1800836a6  mov     rax, [rax+28h]
0x1800836aa  call    cs:__guard_dispatch_icall_fptr
0x1800836b0  jmp     short loc_1800836BB
0x1800836b2  mov     rcx, rdx; Size
0x1800836b5  call    cs:malloc
0x1800836bb  mov     rdi, rax
0x1800836be  test    rax, rax
0x1800836c1  jz      loc_180083785
0x1800836c7  test    sil, sil
0x1800836ca  jz      loc_180083763
0x1800836d0  test    byte ptr [rbx+10h], 80h
0x1800836d4  jz      short loc_1800836DE
0x1800836d6  mov     rcx, rbx
0x1800836d9  call    sub_180086194
0x1800836de  mov     rax, cs:qword_1802B0010
0x1800836e5  mov     rcx, [rax]
0x1800836e8  test    rcx, rcx
0x1800836eb  jz      short loc_1800836FD
0x1800836ed  cmp     rcx, rbx
0x1800836f0  jz      short loc_1800836FD
0x1800836f2  test    byte ptr [rcx+10h], 80h
0x1800836f6  jz      short loc_1800836FD
0x1800836f8  call    sub_180086194
0x1800836fd  mov     ecx, [rbx+0Ch]
0x180083700  test    byte ptr [rbx+10h], 2
0x180083704  jz      short loc_180083714
0x180083706  mov     eax, 1
0x18008370b  lock xadd [rbx+8], eax
0x180083710  inc     eax
0x180083712  jmp     short loc_18008371C
0x180083714  mov     eax, [rbx+8]
0x180083717  inc     eax
0x180083719  mov     [rbx+8], eax
0x18008371c  test    ecx, ecx
0x18008371e  jz      short loc_18008372A
0x180083720  cmp     ecx, eax
0x180083722  jnz     short loc_18008372A
0x180083724  call    cs:DebugBreak
0x18008372a  mov     eax, [rbx+8]
0x18008372d  mov     [rdi], eax
0x18008372f  call    cs:GetCurrentThreadId
0x180083735  or      dword ptr [rdi+10h], 0FFFFFFFFh
0x180083739  mov     rcx, rbx
0x18008373c  mov     [rdi+4], eax
0x18008373f  lea     rax, aUnknownFile; "(unknown file)"
0x180083746  mov     [rdi+8], rax
0x18008374a  mov     [rdi+18h], rbp
0x18008374e  mov     eax, [rsp+38h+arg_8]
0x180083752  mov     [rdi+20h], eax
0x180083755  movsxd  rdx, [rsp+38h+arg_8]
0x18008375a  call    sub_180086284
0x18008375f  add     rdi, 28h ; '('
0x180083763  mov     rbp, [rsp+38h+arg_10]
0x180083768  lea     rax, [rdi+8]
0x18008376c  mov     rsi, [rsp+38h+arg_18]
0x180083771  mov     [rdi], rbx
0x180083774  mov     rbx, [rsp+38h+arg_0]
0x180083779  add     rsp, 30h
0x18008377d  pop     rdi
0x18008377e  retn
0x18008377f  call    sub_1800C34B8
0x180083785  call    sub_1800C34B8
```
