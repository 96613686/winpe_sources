# HEAP::ReadHeap(CTypeLib2 *)

- ea: `0x18000f484`
- end: `0x18000f55d`
- name: `?ReadHeap@HEAP@@QEAAJPEAVCTypeLib2@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(HEAP *__hidden this, struct CTypeLib2 *)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x18000db00`
- `0x18000dd50`
- `0x18000f3a0`
- `0x180010100`
- `0x180010d5c`
- `0x180010d94`
- `0x180010dc8`
- `0x180013f94`
- `0x180015da8`
- `0x180030014`
- `0x180034f48`
- `0x18003f764`
- `0x1800492d0`

## callees

- `0x18000f484`
- `0x18000f900`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f530`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f530`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f4a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f4a6`

## pseudocode

```c
__int64 __fastcall HEAP::ReadHeap(HEAP *this, struct CTypeLib2 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int v5; // edi
  __int64 v6; // rax
  __int64 v7; // r8
  unsigned int v8; // r15d
  unsigned int v9; // r14d
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // ecx
  int v14; // [rsp+60h] [rbp+8h] BYREF
  __int64 v15; // [rsp+68h] [rbp+10h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)a2 + 608);
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 608));
  if ( (*((_BYTE *)this + 12) & 4) == 0 )
  {
    if ( !*((_DWORD *)this + 1) )
    {
      *((_QWORD *)this + 2) = 0;
LABEL_7:
      *((_DWORD *)this + 3) |= 0xCu;
      goto LABEL_8;
    }
    v6 = MemAlloc(*((unsigned int *)this + 1));
    v7 = v6;
    if ( !v6 )
    {
      v5 = -2147024882;
      goto LABEL_8;
    }
    v8 = *(_DWORD *)this;
    v9 = *((_DWORD *)this + 1);
    *((_QWORD *)this + 2) = v6;
    v10 = (__int64 *)*((_QWORD *)a2 + 60);
    v14 = 0;
    v11 = *v10;
    v15 = v8;
    v5 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD, int *))(v11 + 24))(v10, v8, v7, v9, &v14);
    if ( v5 >= 0 )
    {
      v12 = v14;
      *((_DWORD *)a2 + 126) = v8 + v14;
      if ( v9 != v12 )
      {
        v5 = -2147287010;
        goto LABEL_8;
      }
    }
    if ( !v5 )
      goto LABEL_7;
  }
LABEL_8:
  LeaveCriticalSection(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f484  mov     [rsp+arg_10], rbx
0x18000f489  push    rbp
0x18000f48a  push    rsi
0x18000f48b  push    rdi
0x18000f48c  push    r14
0x18000f48e  push    r15
0x18000f490  sub     rsp, 30h
0x18000f494  lea     rbp, [rdx+260h]
0x18000f49b  mov     rbx, rcx
0x18000f49e  mov     rcx, rbp; lpCriticalSection
0x18000f4a1  mov     rsi, rdx
0x18000f4a4  xor     edi, edi
0x18000f4a6  call    cs:__imp_EnterCriticalSection
0x18000f4ac  test    byte ptr [rbx+0Ch], 4
0x18000f4b0  jnz     short loc_18000F52D
0x18000f4b2  cmp     [rbx+4], edi
0x18000f4b5  jz      loc_18000F550
0x18000f4bb  mov     ecx, [rbx+4]
0x18000f4be  call    MemAlloc
0x18000f4c3  mov     r8, rax
0x18000f4c6  test    rax, rax
0x18000f4c9  jz      loc_18000F556
0x18000f4cf  mov     r15d, [rbx]
0x18000f4d2  lea     rdx, [rsp+58h+arg_0]
0x18000f4d7  mov     r14d, [rbx+4]
0x18000f4db  mov     r9d, r14d
0x18000f4de  mov     [rbx+10h], rax
0x18000f4e2  mov     rcx, [rsi+1E0h]
0x18000f4e9  mov     [rsp+58h+arg_0], edi
0x18000f4ed  mov     [rsp+58h+var_38], rdx
0x18000f4f2  mov     dword ptr [rsp+58h+arg_8+4], edi
0x18000f4f6  mov     rax, [rcx]
0x18000f4f9  mov     dword ptr [rsp+58h+arg_8], r15d
0x18000f4fe  mov     rdx, [rsp+58h+arg_8]
0x18000f503  mov     rax, [rax+18h]
0x18000f507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f50c  mov     edi, eax
0x18000f50e  test    eax, eax
0x18000f510  js      short loc_18000F525
0x18000f512  mov     ecx, [rsp+58h+arg_0]
0x18000f516  lea     eax, [r15+rcx]
0x18000f51a  mov     [rsi+1F8h], eax
0x18000f520  cmp     r14d, ecx
0x18000f523  jnz     short loc_18000F549
0x18000f525  test    edi, edi
0x18000f527  jnz     short loc_18000F52D
0x18000f529  or      dword ptr [rbx+0Ch], 0Ch
0x18000f52d  mov     rcx, rbp; lpCriticalSection
0x18000f530  call    cs:__imp_LeaveCriticalSection
0x18000f536  mov     rbx, [rsp+58h+arg_10]
0x18000f53b  mov     eax, edi
0x18000f53d  add     rsp, 30h
0x18000f541  pop     r15
0x18000f543  pop     r14
0x18000f545  pop     rdi
0x18000f546  pop     rsi
0x18000f547  pop     rbp
0x18000f548  retn
0x18000f549  mov     edi, 8003001Eh
0x18000f54e  jmp     short loc_18000F52D
0x18000f550  mov     [rbx+10h], rdi
0x18000f554  jmp     short loc_18000F529
0x18000f556  mov     edi, 8007000Eh
0x18000f55b  jmp     short loc_18000F52D
```
