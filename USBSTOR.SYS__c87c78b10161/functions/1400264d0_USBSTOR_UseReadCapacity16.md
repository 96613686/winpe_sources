# USBSTOR_UseReadCapacity16

- ea: `0x1400264d0`
- end: `0x140026671`
- name: `USBSTOR_UseReadCapacity16`
- size: `417`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140005e50`
- `0x140025d60`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x1400264d0`
- `0x1400266ac`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002657c`
- `ntoskrnl!ExAllocatePool2` at `0x14002657c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002661b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002661b`

## pseudocode

```c
bool __fastcall USBSTOR_UseReadCapacity16(PDEVICE_OBJECT DeviceObject)
{
  _DWORD *DeviceExtension; // rbx
  _DWORD *Pool2; // rdi
  __int128 Src; // [rsp+40h] [rbp-38h] BYREF
  __int64 v6; // [rsp+80h] [rbp+8h] BYREF

  LODWORD(v6) = 8;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  DeviceExtension = DeviceObject->DeviceExtension;
  if ( DeviceExtension[201] == 255 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    DeviceExtension[201] = 1;
    Src = 0;
    Pool2 = (_DWORD *)ExAllocatePool2(64, 8, 1396788565);
    if ( !Pool2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      return 0;
    }
    BYTE1(Src) = 32 * *((_BYTE *)DeviceExtension + 71);
    LOBYTE(Src) = 37;
    if ( (int)USBSTOR_IssueInternalCdbToLun(DeviceObject, (__int64)&v6, &Src, 10, 20) >= 0 && *Pool2 == -1 )
      DeviceExtension[201] = 2;
    ExFreePoolWithTag(Pool2, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return DeviceExtension[201] == 2;
}

```

## disassembly

```asm
0x1400264d0  mov     rax, rsp
0x1400264d3  push    rbx
0x1400264d4  push    rsi
0x1400264d5  push    rdi
0x1400264d6  push    r14
0x1400264d8  sub     rsp, 58h
0x1400264dc  mov     edi, 8
0x1400264e1  mov     rsi, rcx
0x1400264e4  mov     [rax+8], edi
0x1400264e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400264ee  lea     r14, WPP_GLOBAL_Control
0x1400264f5  cmp     rcx, r14
0x1400264f8  jz      short loc_14002651A
0x1400264fa  mov     eax, [rcx+2Ch]
0x1400264fd  test    al, 1
0x1400264ff  jz      short loc_14002651A
0x140026501  cmp     byte ptr [rcx+29h], 4
0x140026505  jb      short loc_14002651A
0x140026507  mov     rcx, [rcx+18h]
0x14002650b  lea     edx, [rdi+22h]
0x14002650e  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140026515  call    WPP_SF_
0x14002651a  mov     rbx, [rsi+40h]
0x14002651e  cmp     dword ptr [rbx+324h], 0FFh
0x140026528  jnz     loc_140026627
0x14002652e  mov     rcx, cs:WPP_GLOBAL_Control
0x140026535  cmp     rcx, r14
0x140026538  jz      short loc_14002655C
0x14002653a  mov     eax, [rcx+2Ch]
0x14002653d  test    al, 1
0x14002653f  jz      short loc_14002655C
0x140026541  cmp     byte ptr [rcx+29h], 4
0x140026545  jb      short loc_14002655C
0x140026547  mov     rcx, [rcx+18h]
0x14002654b  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140026552  mov     edx, 2Bh ; '+'
0x140026557  call    WPP_SF_
0x14002655c  xorps   xmm0, xmm0
0x14002655f  mov     dword ptr [rbx+324h], 1
0x140026569  mov     r8d, 53414D55h
0x14002656f  mov     rdx, rdi
0x140026572  mov     ecx, 40h ; '@'
0x140026577  movups  [rsp+78h+var_38], xmm0
0x14002657c  call    cs:__imp_ExAllocatePool2
0x140026583  nop     dword ptr [rax+rax+00h]
0x140026588  mov     rdi, rax
0x14002658b  test    rax, rax
0x14002658e  jnz     short loc_1400265C3
0x140026590  mov     rcx, cs:WPP_GLOBAL_Control
0x140026597  cmp     rcx, r14
0x14002659a  jz      short loc_1400265BC
0x14002659c  mov     eax, [rcx+2Ch]
0x14002659f  test    al, 1
0x1400265a1  jz      short loc_1400265BC
0x1400265a3  cmp     byte ptr [rcx+29h], 2
0x1400265a7  jb      short loc_1400265BC
0x1400265a9  mov     rcx, [rcx+18h]
0x1400265ad  lea     edx, [rdi+2Ch]
0x1400265b0  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400265b7  call    WPP_SF_
0x1400265bc  xor     al, al
0x1400265be  jmp     loc_140026666
0x1400265c3  mov     dl, [rbx+47h]
0x1400265c6  mov     r9, rdi
0x1400265c9  mov     al, dl
0x1400265cb  mov     [rsp+78h+var_40], 14h; int
0x1400265d3  shl     al, 5
0x1400265d6  mov     rcx, rsi; DeviceObject
0x1400265d9  mov     byte ptr [rsp+78h+var_38+1], al
0x1400265dd  lea     rax, [rsp+78h+var_38]
0x1400265e2  mov     [rsp+78h+var_48], 0Ah; char
0x1400265e7  mov     [rsp+78h+Src], rax; Src
0x1400265ec  lea     rax, [rsp+78h+arg_0]
0x1400265f4  mov     [rsp+78h+var_58], rax; __int64
0x1400265f9  mov     byte ptr [rsp+78h+var_38], 25h ; '%'
0x1400265fe  call    USBSTOR_IssueInternalCdbToLun
0x140026603  test    eax, eax
0x140026605  js      short loc_140026616
0x140026607  cmp     dword ptr [rdi], 0FFFFFFFFh
0x14002660a  jnz     short loc_140026616
0x14002660c  mov     dword ptr [rbx+324h], 2
0x140026616  xor     edx, edx; Tag
0x140026618  mov     rcx, rdi; P
0x14002661b  call    cs:__imp_ExFreePoolWithTag
0x140026622  nop     dword ptr [rax+rax+00h]
0x140026627  mov     rcx, cs:WPP_GLOBAL_Control
0x14002662e  cmp     rcx, r14
0x140026631  jz      short loc_14002665C
0x140026633  mov     eax, [rcx+2Ch]
0x140026636  test    al, 1
0x140026638  jz      short loc_14002665C
0x14002663a  cmp     byte ptr [rcx+29h], 4
0x14002663e  jb      short loc_14002665C
0x140026640  mov     r9d, [rbx+324h]
0x140026647  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14002664e  mov     rcx, [rcx+18h]
0x140026652  mov     edx, 2Dh ; '-'
0x140026657  call    WPP_SF_d
0x14002665c  cmp     dword ptr [rbx+324h], 2
0x140026663  setz    al
0x140026666  add     rsp, 58h
0x14002666a  pop     r14
0x14002666c  pop     rdi
0x14002666d  pop     rsi
0x14002666e  pop     rbx
0x14002666f  retn
```
