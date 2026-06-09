# BiUpdateBcdObject

- ea: `0x140024cf0`
- end: `0x140025154`
- name: `BiUpdateBcdObject`
- size: `1124`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140021f58`

## callees

- `0x1400133e4`
- `0x140013b48`
- `0x140013ee8`
- `0x140018890`
- `0x140018b54`
- `0x140019990`
- `0x14001c794`
- `0x14001f324`
- `0x140020720`
- `0x140022e8c`
- `0x140023f80`
- `0x140024160`
- `0x14002467c`
- `0x140024cf0`
- `0x1400265d6`
- `0x140026650`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140024e77`
- `ntdll!RtlAllocateHeap` at `0x140024e77`
- `ntdll!RtlCompareMemory` at `0x140024e15`
- `ntdll!RtlCompareMemory` at `0x140024eb7`
- `ntdll!RtlCompareMemory` at `0x140024e15`
- `ntdll!RtlCompareMemory` at `0x140024eb7`
- `ntdll!RtlFreeHeap` at `0x140025071`
- `ntdll!RtlFreeHeap` at `0x1400250a0`
- `ntdll!RtlFreeHeap` at `0x1400250c1`
- `ntdll!RtlFreeHeap` at `0x1400250de`
- `ntdll!RtlFreeHeap` at `0x140025108`
- `ntdll!RtlFreeHeap` at `0x140025125`
- `ntdll!RtlFreeHeap` at `0x140025071`
- `ntdll!RtlFreeHeap` at `0x1400250a0`
- `ntdll!RtlFreeHeap` at `0x1400250c1`
- `ntdll!RtlFreeHeap` at `0x1400250de`
- `ntdll!RtlFreeHeap` at `0x140025108`
- `ntdll!RtlFreeHeap` at `0x140025125`

## string_xrefs

- `0x140024d88`: `BiUpdateBcdObject: %wZ Fw:%d`
- `0x140024f06`: `BiUpdateObject: Updating descriptions %ws %ws`

## pseudocode

```c
__int64 __fastcall BiUpdateBcdObject(__int64 a1, __int64 a2)
{
  _DWORD *v2; // rdi
  unsigned int *v4; // r14
  _DWORD *v5; // r15
  void *v6; // r13
  wchar_t *Heap; // r12
  unsigned int *v8; // rsi
  int v9; // eax
  HANDLE v10; // r14
  int v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // r8
  _WORD *v14; // r15
  __int64 v15; // rax
  SIZE_T v16; // rbx
  int ElementDataWithFlags; // eax
  __int64 v18; // r8
  const wchar_t *v19; // r8
  __int64 v20; // rax
  char *v21; // rbx
  _DWORD *v22; // r15
  int v23; // eax
  unsigned int v24; // eax
  SIZE_T Size; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v27; // [rsp+38h] [rbp-81h] BYREF
  unsigned int v28; // [rsp+3Ch] [rbp-7Dh] BYREF
  PVOID P; // [rsp+40h] [rbp-79h] BYREF
  void *Source2; // [rsp+48h] [rbp-71h] BYREF
  __int64 v31; // [rsp+50h] [rbp-69h]
  void *Buf2; // [rsp+58h] [rbp-61h] BYREF
  PVOID v33; // [rsp+60h] [rbp-59h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-51h] BYREF
  _QWORD v35[2]; // [rsp+70h] [rbp-49h] BYREF
  char v36; // [rsp+80h] [rbp-39h] BYREF

  v2 = *(_DWORD **)(a2 + 40);
  v31 = a2;
  v35[0] = 5111808;
  v4 = (unsigned int *)(a2 + 16);
  v27 = 0;
  v5 = (_DWORD *)(a2 + 48);
  v28 = 0;
  v6 = 0;
  v35[1] = &v36;
  Heap = 0;
  P = 0;
  v8 = 0;
  v33 = 0;
  Source2 = 0;
  Handle = 0;
  Size = 0;
  Buf2 = 0;
  if ( byte_14003F840 )
  {
    BiStringFromGUID(v4, (__int64)v35);
    BiLogMessage(1, L"BiUpdateBcdObject: %wZ Fw:%d", v35, (*v5 >> 1) & 1);
  }
  v9 = BcdOpenObject(a1, v4, &Handle);
  v10 = Handle;
  v11 = v9;
  if ( v9 >= 0 )
  {
    if ( (*(_BYTE *)v5 & 2) != 0 )
    {
      if ( (int)BiGetRegistryValue(
                  (unsigned __int64)Handle,
                  L"FirmwareVariable",
                  (__int64)L"Description",
                  3u,
                  &Source2,
                  (ULONG *)&Size + 1) >= 0
        && (v12 = v2[1], v12 == HIDWORD(Size)) )
      {
        v6 = Source2;
        if ( RtlCompareMemory(v2, Source2, v12) == v12 )
          goto LABEL_8;
      }
      else
      {
        v6 = Source2;
      }
    }
    v11 = BiSaveFirmwareVariable(v10, v31 + 16, v2, (unsigned int)v2[1]);
    if ( v11 < 0 )
    {
LABEL_42:
      if ( v6 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      goto LABEL_44;
    }
    *v5 |= 2u;
LABEL_8:
    v14 = (_WORD *)((char *)v2 + (unsigned int)v2[4]);
    v15 = -1;
    do
      ++v15;
    while ( v14[v15] );
    v16 = (unsigned int)(2 * v15 + 2);
    ElementDataWithFlags = BcdGetElementDataWithFlags((__int64)v10, 0x12000004u, v13, 0, &Size);
    if ( ElementDataWithFlags == -1073741789 )
    {
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
      if ( !Heap )
        goto LABEL_22;
      ElementDataWithFlags = BcdGetElementDataWithFlags((__int64)v10, 0x12000004u, v18, (__int64)Heap, &Size);
    }
    if ( ElementDataWithFlags >= 0 )
    {
      if ( !Heap )
        goto LABEL_22;
      if ( (_DWORD)Size != (_DWORD)v16 )
      {
LABEL_18:
        v19 = Heap;
LABEL_23:
        BiLogMessage(1, L"BiUpdateObject: Updating descriptions %ws %ws", v19, v14);
        BiDeleteElement((__int64)v10, 0x12000004u, 1);
        BcdSetElementDataWithFlags((__int64)v10, 301989892, 0, (__int64)v14, v16);
LABEL_24:
        v20 = (unsigned int)v2[5];
        if ( *(_DWORD *)((char *)v2 + v20 + 8) == 4 )
        {
          v21 = (char *)v2 + v20;
          if ( (int)BiGetDeviceFromEfiPath((char *)v2 + v20 + 12, &P, &v27) < 0 )
          {
            v22 = P;
          }
          else
          {
            BiDeleteElement((__int64)v10, 0x11000001u, 1);
            v22 = P;
            BcdSetElementDataWithFlags((__int64)v10, 285212673, 0, (__int64)P, v27);
          }
          if ( (int)BiGetFilePathFromEfiPath((__int64)(v21 + 12), &v33, &v28) >= 0 )
          {
            BiDeleteElement((__int64)v10, 0x12000002u, 1);
            BcdSetElementDataWithFlags((__int64)v10, 301989890, 0, (__int64)v33, v28);
          }
          v23 = BiCreateMergedBootEntry(v2, 0, v22, 0, &Buf2);
          v8 = (unsigned int *)Buf2;
          if ( v23 >= 0 )
          {
            v24 = v2[1];
            if ( v24 != *((_DWORD *)Buf2 + 1) || memcmp_0(v2, Buf2, v24) )
            {
              BiLogMessage(2, L"Updating BootEntry: %d '%ws'", (unsigned int)v2[2], (char *)v2 + (unsigned int)v2[4]);
              v11 = BiModifyBootEntry(v8);
              if ( v11 < 0 )
                goto LABEL_38;
              v11 = BiSaveFirmwareVariable(v10, v31 + 16, v8, v8[1]);
              if ( v11 < 0 )
                goto LABEL_38;
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
              *(_QWORD *)(v31 + 40) = v8;
              v8 = 0;
            }
          }
        }
        else
        {
          v22 = P;
        }
        v11 = 0;
LABEL_38:
        if ( v22 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
        if ( v33 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v33);
        goto LABEL_42;
      }
      if ( RtlCompareMemory(v14, Heap, v16) == v16 )
        goto LABEL_24;
    }
    if ( Heap )
      goto LABEL_18;
LABEL_22:
    v19 = L"<NULL>";
    goto LABEL_23;
  }
LABEL_44:
  if ( v10 )
    BcdCloseObject(v10);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140024cf0  mov     [rsp-8+arg_10], rbx
0x140024cf5  push    rbp
0x140024cf6  push    rsi
0x140024cf7  push    rdi
0x140024cf8  push    r12
0x140024cfa  push    r13
0x140024cfc  push    r14
0x140024cfe  push    r15
0x140024d00  lea     rbp, [rsp-27h]
0x140024d05  sub     rsp, 0E0h
0x140024d0c  mov     rax, cs:__security_cookie
0x140024d13  xor     rax, rsp
0x140024d16  mov     [rbp+57h+var_40], rax
0x140024d1a  mov     rdi, [rdx+28h]
0x140024d1e  lea     rax, [rbp+57h+var_90]
0x140024d22  mov     rbx, rcx
0x140024d25  mov     [rbp+57h+var_C0], rdx
0x140024d29  xor     ecx, ecx
0x140024d2b  mov     [rbp+57h+var_A0], 4E0000h
0x140024d33  cmp     cs:byte_14003F840, cl
0x140024d39  lea     r14, [rdx+10h]
0x140024d3d  mov     [rsp+110h+var_D8], ecx
0x140024d41  lea     r15, [rdx+30h]
0x140024d45  mov     [rbp+57h+var_D4], ecx
0x140024d48  mov     r13d, ecx
0x140024d4b  mov     [rbp+57h+var_98], rax
0x140024d4f  mov     r12d, ecx
0x140024d52  mov     [rbp+57h+P], rcx
0x140024d56  mov     esi, ecx
0x140024d58  mov     [rbp+57h+var_B0], rcx
0x140024d5c  mov     [rbp+57h+Source2], rcx
0x140024d60  mov     dword ptr [rsp+110h+Size+4], ecx
0x140024d64  mov     [rbp+57h+Handle], rcx
0x140024d68  mov     dword ptr [rsp+110h+Size], ecx
0x140024d6c  mov     [rbp+57h+Buf2], rcx
0x140024d70  jz      short loc_140024D9B
0x140024d72  lea     rdx, [rbp+57h+var_A0]
0x140024d76  mov     rcx, r14
0x140024d79  call    BiStringFromGUID
0x140024d7e  mov     r9d, [r15]
0x140024d81  lea     r8, [rbp+57h+var_A0]
0x140024d85  shr     r9d, 1
0x140024d88  lea     rdx, aBiupdatebcdobj; "BiUpdateBcdObject: %wZ Fw:%d"
0x140024d8f  and     r9d, 1
0x140024d93  lea     ecx, [rsi+1]
0x140024d96  call    BiLogMessage
0x140024d9b  lea     r8, [rbp+57h+Handle]
0x140024d9f  mov     rdx, r14
0x140024da2  mov     rcx, rbx
0x140024da5  call    BcdOpenObject
0x140024daa  mov     r14, [rbp+57h+Handle]
0x140024dae  mov     ebx, eax
0x140024db0  test    eax, eax
0x140024db2  js      loc_1400250E4
0x140024db8  test    byte ptr [r15], 2
0x140024dbc  jz      loc_140024ED0
0x140024dc2  lea     rax, [rsp+110h+Size+4]
0x140024dc7  mov     r9d, 3
0x140024dcd  mov     [rsp+110h+var_E8], rax
0x140024dd2  lea     r8, aDescription; "Description"
0x140024dd9  lea     rax, [rbp+57h+Source2]
0x140024ddd  mov     rcx, r14
0x140024de0  lea     rdx, aFirmwarevariab; "FirmwareVariable"
0x140024de7  mov     [rsp+110h+var_F0], rax
0x140024dec  call    BiGetRegistryValue
0x140024df1  test    eax, eax
0x140024df3  js      loc_140024ECC
0x140024df9  mov     eax, [rdi+4]
0x140024dfc  cmp     eax, dword ptr [rsp+110h+Size+4]
0x140024e00  jnz     loc_140024ECC
0x140024e06  mov     r13, [rbp+57h+Source2]
0x140024e0a  mov     r8d, eax; Length
0x140024e0d  mov     rdx, r13; Source2
0x140024e10  mov     rcx, rdi; Source1
0x140024e13  mov     ebx, eax
0x140024e15  call    cs:__imp_RtlCompareMemory
0x140024e1b  cmp     rax, rbx
0x140024e1e  jnz     loc_140024ED0
0x140024e24  xor     ecx, ecx
0x140024e26  mov     r15d, [rdi+10h]
0x140024e2a  add     r15, rdi
0x140024e2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140024e31  inc     rax
0x140024e34  cmp     [r15+rax*2], cx
0x140024e39  jnz     short loc_140024E31
0x140024e3b  lea     ebx, ds:2[rax*2]
0x140024e42  xor     r9d, r9d
0x140024e45  lea     rax, [rsp+110h+Size]
0x140024e4a  mov     edx, 12000004h
0x140024e4f  mov     rcx, r14
0x140024e52  mov     [rsp+110h+var_F0], rax
0x140024e57  call    BcdGetElementDataWithFlags
0x140024e5c  cmp     eax, 0C0000023h
0x140024e61  jnz     short loc_140024E9F
0x140024e63  mov     rcx, gs:60h
0x140024e6c  xor     edx, edx; Flags
0x140024e6e  mov     r8d, dword ptr [rsp+110h+Size]; Size
0x140024e73  mov     rcx, [rcx+30h]; HeapHandle
0x140024e77  call    cs:__imp_RtlAllocateHeap
0x140024e7d  mov     r12, rax
0x140024e80  test    rax, rax
0x140024e83  jz      short loc_140024EFC
0x140024e85  lea     rax, [rsp+110h+Size]
0x140024e8a  mov     r9, r12
0x140024e8d  mov     edx, 12000004h
0x140024e92  mov     [rsp+110h+var_F0], rax
0x140024e97  mov     rcx, r14
0x140024e9a  call    BcdGetElementDataWithFlags
0x140024e9f  test    eax, eax
0x140024ea1  js      short loc_140024EC2
0x140024ea3  test    r12, r12
0x140024ea6  jz      short loc_140024EFC
0x140024ea8  cmp     dword ptr [rsp+110h+Size], ebx
0x140024eac  jnz     short loc_140024EC7
0x140024eae  mov     r8, rbx; Length
0x140024eb1  mov     rdx, r12; Source2
0x140024eb4  mov     rcx, r15; Source1
0x140024eb7  call    cs:__imp_RtlCompareMemory
0x140024ebd  cmp     rax, rbx
0x140024ec0  jz      short loc_140024F3E
0x140024ec2  test    r12, r12
0x140024ec5  jz      short loc_140024EFC
0x140024ec7  mov     r8, r12
0x140024eca  jmp     short loc_140024F03
0x140024ecc  mov     r13, [rbp+57h+Source2]
0x140024ed0  mov     rdx, [rbp+57h+var_C0]
0x140024ed4  mov     r8, rdi
0x140024ed7  mov     r9d, [rdi+4]
0x140024edb  add     rdx, 10h
0x140024edf  mov     rcx, r14
0x140024ee2  call    BiSaveFirmwareVariable
0x140024ee7  xor     ecx, ecx
0x140024ee9  mov     ebx, eax
0x140024eeb  test    eax, eax
0x140024eed  js      loc_1400250C7
0x140024ef3  or      dword ptr [r15], 2
0x140024ef7  jmp     loc_140024E26
0x140024efc  lea     r8, aNull_0; "<NULL>"
0x140024f03  mov     r9, r15
0x140024f06  lea     rdx, aBiupdateobject; "BiUpdateObject: Updating descriptions %"...
0x140024f0d  mov     ecx, 1
0x140024f12  call    BiLogMessage
0x140024f17  mov     r8b, 1
0x140024f1a  mov     edx, 12000004h
0x140024f1f  mov     rcx, r14
0x140024f22  call    BiDeleteElement
0x140024f27  mov     r9, r15
0x140024f2a  mov     dword ptr [rsp+110h+var_F0], ebx
0x140024f2e  xor     r8d, r8d
0x140024f31  mov     edx, 12000004h
0x140024f36  mov     rcx, r14
0x140024f39  call    BcdSetElementDataWithFlags
0x140024f3e  mov     eax, [rdi+14h]
0x140024f41  cmp     dword ptr [rax+rdi+8], 4
0x140024f46  jnz     loc_140025083
0x140024f4c  lea     rbx, [rax+rdi]
0x140024f50  lea     rcx, [rbx+0Ch]; Src
0x140024f54  lea     r8, [rsp+110h+var_D8]
0x140024f59  lea     rdx, [rbp+57h+P]
0x140024f5d  call    BiGetDeviceFromEfiPath
0x140024f62  test    eax, eax
0x140024f64  js      short loc_140024F96
0x140024f66  mov     esi, 11000001h
0x140024f6b  mov     r8b, 1
0x140024f6e  mov     edx, esi
0x140024f70  mov     rcx, r14
0x140024f73  call    BiDeleteElement
0x140024f78  mov     eax, [rsp+110h+var_D8]
0x140024f7c  xor     r8d, r8d
0x140024f7f  mov     r15, [rbp+57h+P]
0x140024f83  mov     edx, esi
0x140024f85  mov     r9, r15
0x140024f88  mov     dword ptr [rsp+110h+var_F0], eax
0x140024f8c  mov     rcx, r14
0x140024f8f  call    BcdSetElementDataWithFlags
0x140024f94  jmp     short loc_140024F9A
0x140024f96  mov     r15, [rbp+57h+P]
0x140024f9a  lea     r8, [rbp+57h+var_D4]
0x140024f9e  lea     rdx, [rbp+57h+var_B0]
0x140024fa2  lea     rcx, [rbx+0Ch]
0x140024fa6  call    BiGetFilePathFromEfiPath
0x140024fab  test    eax, eax
0x140024fad  js      short loc_140024FD9
0x140024faf  mov     ebx, 12000002h
0x140024fb4  mov     r8b, 1
0x140024fb7  mov     edx, ebx
0x140024fb9  mov     rcx, r14
0x140024fbc  call    BiDeleteElement
0x140024fc1  mov     eax, [rbp+57h+var_D4]
0x140024fc4  xor     r8d, r8d
0x140024fc7  mov     r9, [rbp+57h+var_B0]
0x140024fcb  mov     edx, ebx
0x140024fcd  mov     rcx, r14
0x140024fd0  mov     dword ptr [rsp+110h+var_F0], eax
0x140024fd4  call    BcdSetElementDataWithFlags
0x140024fd9  lea     rax, [rbp+57h+Buf2]
0x140024fdd  xor     r9d, r9d
0x140024fe0  mov     r8, r15
0x140024fe3  mov     [rsp+110h+var_F0], rax
0x140024fe8  xor     edx, edx
0x140024fea  mov     rcx, rdi
0x140024fed  call    BiCreateMergedBootEntry
0x140024ff2  mov     rsi, [rbp+57h+Buf2]
0x140024ff6  test    eax, eax
0x140024ff8  js      loc_140025087
0x140024ffe  mov     eax, [rdi+4]
0x140025001  cmp     eax, [rsi+4]
0x140025004  jnz     short loc_140025018
0x140025006  mov     r8d, eax; Size
0x140025009  mov     rdx, rsi; Buf2
0x14002500c  mov     rcx, rdi; Buf1
0x14002500f  call    memcmp_0
0x140025014  test    eax, eax
0x140025016  jz      short loc_140025087
0x140025018  mov     r9d, [rdi+10h]
0x14002501c  lea     rdx, aUpdatingBooten; "Updating BootEntry: %d '%ws'"
0x140025023  mov     r8d, [rdi+8]
0x140025027  add     r9, rdi
0x14002502a  mov     ecx, 2
0x14002502f  call    BiLogMessage
0x140025034  mov     rcx, rsi
0x140025037  call    BiModifyBootEntry
0x14002503c  mov     ebx, eax
0x14002503e  test    eax, eax
0x140025040  js      short loc_140025089
0x140025042  mov     rdx, [rbp+57h+var_C0]
0x140025046  mov     r8, rsi
0x140025049  mov     r9d, [rsi+4]
0x14002504d  add     rdx, 10h
0x140025051  mov     rcx, r14
0x140025054  call    BiSaveFirmwareVariable
0x140025059  mov     ebx, eax
0x14002505b  test    eax, eax
0x14002505d  js      short loc_140025089
0x14002505f  mov     rcx, gs:60h
0x140025068  mov     r8, rdi; P
0x14002506b  xor     edx, edx; Flags
0x14002506d  mov     rcx, [rcx+30h]; HeapHandle
0x140025071  call    cs:__imp_RtlFreeHeap
0x140025077  mov     rax, [rbp+57h+var_C0]
0x14002507b  mov     [rax+28h], rsi
0x14002507f  xor     esi, esi
0x140025081  jmp     short loc_140025087
0x140025083  mov     r15, [rbp+57h+P]
0x140025087  xor     ebx, ebx
0x140025089  test    r15, r15
0x14002508c  jz      short loc_1400250A6
0x14002508e  mov     rcx, gs:60h
0x140025097  mov     r8, r15; P
0x14002509a  xor     edx, edx; Flags
0x14002509c  mov     rcx, [rcx+30h]; HeapHandle
0x1400250a0  call    cs:__imp_RtlFreeHeap
0x1400250a6  mov     rax, [rbp+57h+var_B0]
0x1400250aa  test    rax, rax
0x1400250ad  jz      short loc_1400250C7
0x1400250af  mov     rcx, gs:60h
0x1400250b8  mov     r8, rax; P
0x1400250bb  xor     edx, edx; Flags
0x1400250bd  mov     rcx, [rcx+30h]; HeapHandle
0x1400250c1  call    cs:__imp_RtlFreeHeap
0x1400250c7  test    r13, r13
0x1400250ca  jz      short loc_1400250E4
0x1400250cc  mov     rcx, gs:60h
0x1400250d5  mov     r8, r13; P
0x1400250d8  xor     edx, edx; Flags
0x1400250da  mov     rcx, [rcx+30h]; HeapHandle
0x1400250de  call    cs:__imp_RtlFreeHeap
0x1400250e4  test    r14, r14
0x1400250e7  jz      short loc_1400250F1
0x1400250e9  mov     rcx, r14; Handle
0x1400250ec  call    BcdCloseObject
0x1400250f1  test    r12, r12
0x1400250f4  jz      short loc_14002510E
0x1400250f6  mov     rcx, gs:60h
0x1400250ff  mov     r8, r12; P
0x140025102  xor     edx, edx; Flags
0x140025104  mov     rcx, [rcx+30h]; HeapHandle
0x140025108  call    cs:__imp_RtlFreeHeap
0x14002510e  test    rsi, rsi
0x140025111  jz      short loc_14002512B
0x140025113  mov     rcx, gs:60h
0x14002511c  mov     r8, rsi; P
0x14002511f  xor     edx, edx; Flags
0x140025121  mov     rcx, [rcx+30h]; HeapHandle
0x140025125  call    cs:__imp_RtlFreeHeap
0x14002512b  mov     eax, ebx
0x14002512d  mov     rcx, [rbp+57h+var_40]
0x140025131  xor     rcx, rsp; StackCookie
0x140025134  call    __security_check_cookie
0x140025139  mov     rbx, [rsp+110h+arg_10]
0x140025141  add     rsp, 0E0h
0x140025148  pop     r15
0x14002514a  pop     r14
0x14002514c  pop     r13
0x14002514e  pop     r12
0x140025150  pop     rdi
0x140025151  pop     rsi
0x140025152  pop     rbp
0x140025153  retn
```
