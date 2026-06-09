# AhcCdbLookup

- ea: `0x140049520`
- end: `0x140049626`
- name: `AhcCdbLookup`
- size: `262`
- prototype: `__int64 __fastcall(_DWORD *, __int64, _OWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140049bfc`
- `0x140055898`

## callees

- `0x14003e364`
- `0x140049520`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140049583`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140049583`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004953f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004953f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400495d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400495d1`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x140049550`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x140049550`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400495aa`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400495aa`

## string_xrefs

- `0x1400495dd`: `Failed to acquire a lock supporting shared access`
- `0x140049600`: `Failed to acquire a shared cache lock [%x]`

## pseudocode

```c
__int64 __fastcall AhcCdbLookup(_DWORD *a1, __int64 a2, _OWORD *a3)
{
  struct _ERESOURCE *v3; // rdi
  struct _RTL_AVL_TABLE *v7; // rcx
  volatile signed __int32 *v8; // rax
  unsigned int v9; // edi
  unsigned int v11; // ebx
  _OWORD Buffer[5]; // [rsp+30h] [rbp-58h] BYREF

  v3 = *(struct _ERESOURCE **)a2;
  if ( !*(_QWORD *)a2 )
  {
    v11 = -1073741811;
LABEL_9:
    AslLogCallPrintf(1, "AhcCdbLookup", 1385, "Failed to acquire a shared cache lock [%x]", v11);
    return v11;
  }
  KeEnterCriticalRegion();
  if ( !ExAcquireSharedStarveExclusive(v3, 1u) )
  {
    KeLeaveCriticalRegion();
    AslLogCallPrintf(1, "AhcLockAcquireSharedWait", 329, "Failed to acquire a lock supporting shared access");
    v11 = -1073741790;
    goto LABEL_9;
  }
  v7 = *(struct _RTL_AVL_TABLE **)(a2 + 8);
  memset(Buffer, 0, 48);
  *(_OWORD *)((char *)&Buffer[1] + 8) = *a3;
  v8 = (volatile signed __int32 *)RtlLookupElementGenericTableAvl(v7, Buffer);
  if ( v8 )
  {
    _InterlockedIncrement(v8 + 4);
    v9 = 0;
    *a1 = **((_DWORD **)v8 + 5);
    _InterlockedDecrement(v8 + 4);
  }
  else
  {
    v9 = -1073741275;
  }
  ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)a2);
  return v9;
}

```

## disassembly

```asm
0x140049520  push    rbx
0x140049522  push    rsi
0x140049523  push    rdi
0x140049524  push    r14
0x140049526  sub     rsp, 68h
0x14004952a  mov     rdi, [rdx]
0x14004952d  mov     rsi, r8
0x140049530  mov     rbx, rdx
0x140049533  mov     r14, rcx
0x140049536  test    rdi, rdi
0x140049539  jz      loc_1400495CA
0x14004953f  call    cs:__imp_KeEnterCriticalRegion
0x140049546  nop     dword ptr [rax+rax+00h]
0x14004954b  mov     dl, 1; Wait
0x14004954d  mov     rcx, rdi; Resource
0x140049550  call    cs:__imp_ExAcquireSharedStarveExclusive
0x140049557  nop     dword ptr [rax+rax+00h]
0x14004955c  test    al, al
0x14004955e  jz      short loc_1400495D1
0x140049560  mov     rcx, [rbx+8]; Table
0x140049564  lea     rdx, [rsp+88h+Buffer]; Buffer
0x140049569  xorps   xmm0, xmm0
0x14004956c  movups  [rsp+88h+var_48], xmm0
0x140049571  movups  [rsp+88h+var_38], xmm0
0x140049576  movups  [rsp+88h+Buffer], xmm0
0x14004957b  movups  xmm0, xmmword ptr [rsi]
0x14004957e  movups  [rsp+88h+var_48+8], xmm0
0x140049583  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14004958a  nop     dword ptr [rax+rax+00h]
0x14004958f  test    rax, rax
0x140049592  jz      short loc_1400495C3
0x140049594  lock inc dword ptr [rax+10h]
0x140049598  mov     rcx, [rax+28h]
0x14004959c  xor     edi, edi
0x14004959e  mov     edx, [rcx]
0x1400495a0  mov     [r14], edx
0x1400495a3  lock dec dword ptr [rax+10h]
0x1400495a7  mov     rcx, [rbx]; Resource
0x1400495aa  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400495b1  nop     dword ptr [rax+rax+00h]
0x1400495b6  mov     eax, edi
0x1400495b8  add     rsp, 68h
0x1400495bc  pop     r14
0x1400495be  pop     rdi
0x1400495bf  pop     rsi
0x1400495c0  pop     rbx
0x1400495c1  retn
0x1400495c3  mov     edi, 0C0000225h
0x1400495c8  jmp     short loc_1400495A7
0x1400495ca  mov     ebx, 0C000000Dh
0x1400495cf  jmp     short loc_140049600
0x1400495d1  call    cs:__imp_KeLeaveCriticalRegion
0x1400495d8  nop     dword ptr [rax+rax+00h]
0x1400495dd  lea     r9, aFailedToAcquir_3; "Failed to acquire a lock supporting sha"...
0x1400495e4  mov     r8d, 149h
0x1400495ea  lea     rdx, aAhclockacquire; "AhcLockAcquireSharedWait"
0x1400495f1  mov     ecx, 1
0x1400495f6  call    AslLogCallPrintf
0x1400495fb  mov     ebx, 0C0000022h
0x140049600  lea     r9, aFailedToAcquir; "Failed to acquire a shared cache lock ["...
0x140049607  mov     [rsp+88h+var_68], ebx
0x14004960b  mov     r8d, 569h
0x140049611  lea     rdx, aAhccdblookup; "AhcCdbLookup"
0x140049618  mov     ecx, 1
0x14004961d  call    AslLogCallPrintf
0x140049622  mov     eax, ebx
0x140049624  jmp     short loc_1400495B8
```
