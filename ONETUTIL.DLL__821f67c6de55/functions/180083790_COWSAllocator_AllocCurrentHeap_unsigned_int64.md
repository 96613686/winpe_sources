# COWSAllocator::AllocCurrentHeap(unsigned __int64)

- ea: `0x180083790`
- end: `0x1800838e4`
- name: `?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z`
- size: `340`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `582`
- callee_count: `5`
- tags: ``

## callers

- `0x1800039d0`
- `0x180003a40`
- `0x180003bf0`
- `0x180003da0`
- `0x180003e10`
- `0x180003f70`
- `0x180006d80`
- `0x180006e00`
- `0x180007000`
- `0x1800073d0`
- `0x180007460`
- `0x1800076b0`
- `0x18000781c`
- `0x180007c20`
- `0x180007d20`
- `0x180007e00`
- `0x180007ef0`
- `0x1800080b0`
- `0x180008b50`
- `0x180008f48`
- `0x1800092c4`
- `0x18000982c`
- `0x180009f08`
- `0x18000a0b8`
- `0x18000a370`
- `0x18000a4c0`
- `0x18000a620`
- `0x18000a830`
- `0x18000ae20`
- `0x18000b1c0`
- `0x18000b47c`
- `0x18000bad0`
- `0x18000c370`
- `0x18000cbf0`
- `0x18000e8cc`
- `0x18000ecac`
- `0x18000f6a4`
- `0x180010b80`
- `0x180010c20`
- `0x180010e30`
- `0x180011390`
- `0x180011410`
- `0x180011630`
- `0x1800116b0`
- `0x180011730`
- `0x1800117b0`
- `0x180011830`
- `0x180011910`
- `0x180011e80`
- `0x180011f20`

## callees

- `0x180083790`
- `0x180086194`
- `0x180086284`
- `0x1800c34b8`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18008387d`
- `KERNEL32!DebugBreak` at `0x18008387d`
- `KERNEL32!TlsGetValue` at `0x1800837ad`
- `KERNEL32!TlsGetValue` at `0x1800837ad`
- `KERNEL32!GetCurrentThreadId` at `0x180083888`
- `KERNEL32!GetCurrentThreadId` at `0x180083888`

## pseudocode

```c
void *__fastcall COWSAllocator::AllocCurrentHeap(unsigned __int64 a1)
{
  _QWORD *Value; // rax
  __int64 *v3; // rbx
  __int64 v4; // rcx
  char v5; // si
  unsigned __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rcx
  int v10; // ecx
  int v11; // eax
  DWORD CurrentThreadId; // eax
  void *result; // rax
  int v14; // [rsp+40h] [rbp+8h] BYREF

  Value = TlsGetValue(dword_1802AF500);
  if ( Value )
    v3 = (__int64 *)Value[1];
  else
    v3 = *(__int64 **)qword_1802B0010;
  v4 = *v3;
  v5 = 0;
  if ( a1 > 0x40000000 )
    sub_1800C34B8(v4);
  v6 = (((a1 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 8) & 0xFFFFFFF8;
  if ( (v3[2] & 0x20) != 0 )
  {
    v5 = 1;
    v6 = (v6 + 47) & 0xFFFFFFF8;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, int *, _QWORD))(*(_QWORD *)v4 + 40LL))(v4, v6, &v14, 0);
  if ( !v8 )
    sub_1800C34B8(v7);
  if ( v5 )
  {
    if ( *((char *)v3 + 16) < 0 )
      sub_180086194(v3);
    v9 = *(_QWORD *)qword_1802B0010;
    if ( *(_QWORD *)qword_1802B0010 && (__int64 *)v9 != v3 && *(char *)(v9 + 16) < 0 )
      sub_180086194(v9);
    v10 = *((_DWORD *)v3 + 3);
    if ( (v3[2] & 2) != 0 )
    {
      v11 = _InterlockedIncrement((volatile signed __int32 *)v3 + 2);
    }
    else
    {
      v11 = *((_DWORD *)v3 + 2) + 1;
      *((_DWORD *)v3 + 2) = v11;
    }
    if ( v10 && v10 == v11 )
      DebugBreak();
    *(_DWORD *)v8 = *((_DWORD *)v3 + 2);
    CurrentThreadId = GetCurrentThreadId();
    *(_DWORD *)(v8 + 16) = -1;
    *(_DWORD *)(v8 + 4) = CurrentThreadId;
    *(_QWORD *)(v8 + 8) = "(unknown file)";
    *(_QWORD *)(v8 + 24) = a1;
    *(_DWORD *)(v8 + 32) = v14;
    sub_180086284(v3, v14);
    v8 += 40;
  }
  result = (void *)(v8 + 8);
  *(_QWORD *)v8 = v3;
  return result;
}

```

## disassembly

```asm
0x180083790  mov     [rsp+arg_8], rbx
0x180083795  mov     [rsp+arg_10], rbp
0x18008379a  mov     [rsp+arg_18], rsi
0x18008379f  push    rdi
0x1800837a0  sub     rsp, 30h
0x1800837a4  mov     rbp, rcx
0x1800837a7  mov     ecx, cs:dword_1802AF500; dwTlsIndex
0x1800837ad  call    cs:TlsGetValue
0x1800837b3  test    rax, rax
0x1800837b6  jz      short loc_1800837BE
0x1800837b8  mov     rbx, [rax+8]
0x1800837bc  jmp     short loc_1800837C8
0x1800837be  mov     rax, cs:qword_1802B0010
0x1800837c5  mov     rbx, [rax]
0x1800837c8  mov     rcx, [rbx]
0x1800837cb  xor     sil, sil
0x1800837ce  cmp     rbp, 40000000h
0x1800837d5  ja      loc_1800838D8
0x1800837db  lea     rdx, [rbp+7]
0x1800837df  mov     eax, 0FFFFFFF8h
0x1800837e4  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800837e8  add     rdx, 8
0x1800837ec  and     rdx, rax
0x1800837ef  test    byte ptr [rbx+10h], 20h
0x1800837f3  jz      short loc_1800837FF
0x1800837f5  add     rdx, 2Fh ; '/'
0x1800837f9  mov     sil, 1
0x1800837fc  and     rdx, rax
0x1800837ff  mov     rax, [rcx]
0x180083802  lea     r8, [rsp+38h+arg_0]
0x180083807  xor     r9d, r9d
0x18008380a  mov     rax, [rax+28h]
0x18008380e  call    cs:__guard_dispatch_icall_fptr
0x180083814  mov     rdi, rax
0x180083817  test    rax, rax
0x18008381a  jz      loc_1800838DE
0x180083820  test    sil, sil
0x180083823  jz      loc_1800838BC
0x180083829  test    byte ptr [rbx+10h], 80h
0x18008382d  jz      short loc_180083837
0x18008382f  mov     rcx, rbx
0x180083832  call    sub_180086194
0x180083837  mov     rax, cs:qword_1802B0010
0x18008383e  mov     rcx, [rax]
0x180083841  test    rcx, rcx
0x180083844  jz      short loc_180083856
0x180083846  cmp     rcx, rbx
0x180083849  jz      short loc_180083856
0x18008384b  test    byte ptr [rcx+10h], 80h
0x18008384f  jz      short loc_180083856
0x180083851  call    sub_180086194
0x180083856  mov     ecx, [rbx+0Ch]
0x180083859  test    byte ptr [rbx+10h], 2
0x18008385d  jz      short loc_18008386D
0x18008385f  mov     eax, 1
0x180083864  lock xadd [rbx+8], eax
0x180083869  inc     eax
0x18008386b  jmp     short loc_180083875
0x18008386d  mov     eax, [rbx+8]
0x180083870  inc     eax
0x180083872  mov     [rbx+8], eax
0x180083875  test    ecx, ecx
0x180083877  jz      short loc_180083883
0x180083879  cmp     ecx, eax
0x18008387b  jnz     short loc_180083883
0x18008387d  call    cs:DebugBreak
0x180083883  mov     eax, [rbx+8]
0x180083886  mov     [rdi], eax
0x180083888  call    cs:GetCurrentThreadId
0x18008388e  or      dword ptr [rdi+10h], 0FFFFFFFFh
0x180083892  mov     rcx, rbx
0x180083895  mov     [rdi+4], eax
0x180083898  lea     rax, aUnknownFile; "(unknown file)"
0x18008389f  mov     [rdi+8], rax
0x1800838a3  mov     [rdi+18h], rbp
0x1800838a7  mov     eax, [rsp+38h+arg_0]
0x1800838ab  mov     [rdi+20h], eax
0x1800838ae  movsxd  rdx, [rsp+38h+arg_0]
0x1800838b3  call    sub_180086284
0x1800838b8  add     rdi, 28h ; '('
0x1800838bc  mov     rbp, [rsp+38h+arg_10]
0x1800838c1  lea     rax, [rdi+8]
0x1800838c5  mov     rsi, [rsp+38h+arg_18]
0x1800838ca  mov     [rdi], rbx
0x1800838cd  mov     rbx, [rsp+38h+arg_8]
0x1800838d2  add     rsp, 30h
0x1800838d6  pop     rdi
0x1800838d7  retn
0x1800838d8  call    sub_1800C34B8
0x1800838de  call    sub_1800C34B8
```
