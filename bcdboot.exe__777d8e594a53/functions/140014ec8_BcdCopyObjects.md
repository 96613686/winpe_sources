# BcdCopyObjects

- ea: `0x140014ec8`
- end: `0x140015088`
- name: `BcdCopyObjects`
- size: `448`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int, __int64)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400052bc`
- `0x14000583c`
- `0x1400058e4`
- `0x140005ae8`

## callees

- `0x1400133e4`
- `0x140013b48`
- `0x140013c1c`
- `0x140013ee8`
- `0x14001474c`
- `0x140014ec8`
- `0x14001ae94`
- `0x14001c014`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140014f7e`
- `ntdll!RtlAllocateHeap` at `0x140014f7e`
- `ntdll!RtlFreeHeap` at `0x14001505f`
- `ntdll!RtlFreeHeap` at `0x14001505f`

## string_xrefs

- `0x140014f30`: `Copying objects. Version: %d. Type: 0x%08x`

## pseudocode

```c
__int64 __fastcall BcdCopyObjects(__int64 a1, unsigned int *a2, unsigned int a3, __int64 a4)
{
  bool v4; // di
  __int64 v7; // r15
  __int64 result; // rax
  char *Heap; // rsi
  __int64 v10; // rcx
  int v11; // ebx
  __int64 v12; // r14
  SIZE_T Size; // [rsp+30h] [rbp-20h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-18h] BYREF
  HANDLE v15[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v17; // [rsp+90h] [rbp+40h]

  v17 = a3;
  v4 = 0;
  Handle = 0;
  v16 = 0;
  v15[0] = 0;
  v7 = a1;
  if ( (a1 & 1) != 0 )
    v4 = (a4 & 1) != 0;
  LOBYTE(a1) = v4;
  result = BiAcquireBcdSyncMutant(a1);
  if ( (int)result >= 0 )
  {
    Heap = 0;
    BiLogMessage(2, L"Copying objects. Version: %d. Type: 0x%08x", *a2, a2[1]);
    LODWORD(Size) = 0;
    v11 = BcdEnumerateObjects(v7, (_DWORD)a2, 0, (unsigned int)&Size, (__int64)&v16);
    if ( v11 == -1073741789 )
    {
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
      if ( !Heap )
      {
        v11 = -1073741801;
LABEL_17:
        LOBYTE(v10) = v4;
        BiReleaseBcdSyncMutant(v10);
        return (unsigned int)v11;
      }
      v11 = BcdEnumerateObjects(v7, (_DWORD)a2, (_DWORD)Heap, (unsigned int)&Size, (__int64)&v16);
    }
    if ( v11 >= 0 )
    {
      v12 = 0;
      if ( v16 )
      {
        while ( 1 )
        {
          v11 = BcdOpenObject(v7, &Heap[24 * v12], &Handle);
          if ( v11 < 0 )
            break;
          v11 = BcdCopyObjectEx(v7, (__int64)Handle, v17, a4, 0, v15);
          BcdCloseObject(Handle);
          Handle = 0;
          if ( v11 < 0 )
            break;
          BcdCloseObject(v15[0]);
          v12 = (unsigned int)(v12 + 1);
          v15[0] = 0;
          if ( (unsigned int)v12 >= v16 )
            goto LABEL_14;
        }
      }
      else
      {
LABEL_14:
        v11 = 0;
      }
    }
    else
    {
      BiLogMessage(4, L"Failed to enumerate objects. Status: %x", (unsigned int)v11);
    }
    if ( Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x140014ec8  mov     [rsp-28h+arg_8], rbx
0x140014ecd  mov     [rsp-28h+arg_18], rsi
0x140014ed2  mov     [rsp-28h+arg_10], r8d
0x140014ed7  push    rbp
0x140014ed8  push    rdi
0x140014ed9  push    r13
0x140014edb  push    r14
0x140014edd  push    r15
0x140014edf  mov     rbp, rsp
0x140014ee2  sub     rsp, 50h
0x140014ee6  xor     dil, dil
0x140014ee9  mov     [rbp+Handle], 0
0x140014ef1  mov     eax, 1
0x140014ef6  mov     [rbp+arg_0], 0
0x140014efd  mov     [rbp+var_10], 0
0x140014f05  mov     r13, r9
0x140014f08  mov     r14, rdx
0x140014f0b  mov     r15, rcx
0x140014f0e  test    al, cl
0x140014f10  jz      short loc_140014F1C
0x140014f12  test    al, r13b
0x140014f15  movzx   edi, dil
0x140014f19  cmovnz  edi, eax
0x140014f1c  mov     cl, dil
0x140014f1f  call    BiAcquireBcdSyncMutant
0x140014f24  test    eax, eax
0x140014f26  js      loc_14001506F
0x140014f2c  mov     r9d, [r14+4]
0x140014f30  lea     rdx, aCopyingObjects; "Copying objects. Version: %d. Type: 0x%"...
0x140014f37  mov     r8d, [r14]
0x140014f3a  xor     esi, esi
0x140014f3c  lea     ecx, [rsi+2]
0x140014f3f  call    BiLogMessage
0x140014f44  lea     rax, [rbp+arg_0]
0x140014f48  mov     dword ptr [rbp+Size], esi
0x140014f4b  lea     r9, [rbp+Size]
0x140014f4f  mov     [rsp+50h+var_30], rax
0x140014f54  xor     r8d, r8d
0x140014f57  mov     rdx, r14
0x140014f5a  mov     rcx, r15
0x140014f5d  call    BcdEnumerateObjects
0x140014f62  mov     ebx, eax
0x140014f64  cmp     eax, 0C0000023h
0x140014f69  jnz     short loc_140014FB3
0x140014f6b  mov     rcx, gs:60h
0x140014f74  xor     edx, edx; Flags
0x140014f76  mov     r8d, dword ptr [rbp+Size]; Size
0x140014f7a  mov     rcx, [rcx+30h]; HeapHandle
0x140014f7e  call    cs:__imp_RtlAllocateHeap
0x140014f84  mov     rsi, rax
0x140014f87  test    rax, rax
0x140014f8a  jnz     short loc_140014F96
0x140014f8c  mov     ebx, 0C0000017h
0x140014f91  jmp     loc_140015065
0x140014f96  lea     rax, [rbp+arg_0]
0x140014f9a  mov     r8, rsi
0x140014f9d  lea     r9, [rbp+Size]
0x140014fa1  mov     [rsp+50h+var_30], rax
0x140014fa6  mov     rdx, r14
0x140014fa9  mov     rcx, r15
0x140014fac  call    BcdEnumerateObjects
0x140014fb1  mov     ebx, eax
0x140014fb3  test    ebx, ebx
0x140014fb5  jns     short loc_140014FCD
0x140014fb7  mov     r8d, ebx
0x140014fba  lea     rdx, aFailedToEnumer_5; "Failed to enumerate objects. Status: %x"
0x140014fc1  mov     ecx, 4
0x140014fc6  call    BiLogMessage
0x140014fcb  jmp     short loc_140015048
0x140014fcd  xor     r14d, r14d
0x140014fd0  cmp     [rbp+arg_0], r14d
0x140014fd4  jbe     short loc_140015046
0x140014fd6  lea     rcx, [r14+r14*2]
0x140014fda  lea     rdx, [rsi+rcx*8]
0x140014fde  mov     rcx, r15
0x140014fe1  lea     r8, [rbp+Handle]
0x140014fe5  call    BcdOpenObject
0x140014fea  mov     ebx, eax
0x140014fec  test    eax, eax
0x140014fee  js      short loc_140015048
0x140014ff0  mov     r8d, [rbp+arg_10]
0x140014ff4  lea     rax, [rbp+var_10]
0x140014ff8  mov     rdx, [rbp+Handle]
0x140014ffc  mov     r9, r13
0x140014fff  mov     [rsp+50h+var_28], rax
0x140015004  mov     rcx, r15
0x140015007  mov     [rsp+50h+var_30], 0
0x140015010  call    BcdCopyObjectEx
0x140015015  mov     rcx, [rbp+Handle]; Handle
0x140015019  mov     ebx, eax
0x14001501b  call    BcdCloseObject
0x140015020  mov     [rbp+Handle], 0
0x140015028  test    ebx, ebx
0x14001502a  js      short loc_140015048
0x14001502c  mov     rcx, [rbp+var_10]; Handle
0x140015030  call    BcdCloseObject
0x140015035  inc     r14d
0x140015038  mov     [rbp+var_10], 0
0x140015040  cmp     r14d, [rbp+arg_0]
0x140015044  jb      short loc_140014FD6
0x140015046  xor     ebx, ebx
0x140015048  test    rsi, rsi
0x14001504b  jz      short loc_140015065
0x14001504d  mov     rcx, gs:60h
0x140015056  mov     r8, rsi; P
0x140015059  xor     edx, edx; Flags
0x14001505b  mov     rcx, [rcx+30h]; HeapHandle
0x14001505f  call    cs:__imp_RtlFreeHeap
0x140015065  mov     cl, dil
0x140015068  call    BiReleaseBcdSyncMutant
0x14001506d  mov     eax, ebx
0x14001506f  lea     r11, [rsp+50h+var_s0]
0x140015074  mov     rbx, [r11+38h]
0x140015078  mov     rsi, [r11+48h]
0x14001507c  mov     rsp, r11
0x14001507f  pop     r15
0x140015081  pop     r14
0x140015083  pop     r13
0x140015085  pop     rdi
0x140015086  pop     rbp
0x140015087  retn
```
