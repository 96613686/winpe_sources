# CNdisSpinLock::CreateInstance(CNdisSpinLock * *)

- ea: `0x1400687e0`
- end: `0x1400688c1`
- name: `?CreateInstance@CNdisSpinLock@@SAHPEAPEAV1@@Z`
- size: `225`
- prototype: `__int64 __fastcall(struct CNdisSpinLock **)`
- caller_count: `11`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140068504`
- `0x1400686f8`
- `0x140077e34`
- `0x14007d678`
- `0x14007e60c`
- `0x1400837c8`
- `0x14009b458`
- `0x14009c670`
- `0x14009fb14`
- `0x1400b9b74`
- `0x1400d6780`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x1400687e0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14006885f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006885f`
- `ntoskrnl!ExAllocatePool2` at `0x140068844`
- `ntoskrnl!ExAllocatePool2` at `0x140068844`

## pseudocode

```c
__int64 __fastcall CNdisSpinLock::CreateInstance(struct CNdisSpinLock **a1)
{
  __int64 Pool2; // rax
  int v3; // edx
  struct CNdisSpinLock *v4; // rdi
  unsigned int v5; // ebx

  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      11,
      (__int64)WPP_dd9b415377a4308d852bb4bfc0c1e026_Traceguids);
  }
  Pool2 = ExAllocatePool2(64, 24, 1198089303);
  v4 = (struct CNdisSpinLock *)Pool2;
  if ( Pool2 )
  {
    *(_BYTE *)(Pool2 + 16) = 0;
    KeInitializeSpinLock((PKSPIN_LOCK)Pool2);
    v5 = 0;
    *a1 = v4;
  }
  else
  {
    v5 = -1073741670;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v3) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      1,
      12,
      (__int64)WPP_dd9b415377a4308d852bb4bfc0c1e026_Traceguids,
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x1400687e0  push    rbx
0x1400687e2  push    rbp
0x1400687e3  push    rsi
0x1400687e4  push    rdi
0x1400687e5  push    r12
0x1400687e7  push    r14
0x1400687e9  sub     rsp, 38h
0x1400687ed  mov     rsi, rcx
0x1400687f0  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400687f7  xor     ebp, ebp
0x1400687f9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140068800  lea     r12, WPP_dd9b415377a4308d852bb4bfc0c1e026_Traceguids
0x140068807  jz      short loc_140068836
0x140068809  mov     rcx, cs:WPP_GLOBAL_Control
0x140068810  cmp     byte ptr [rcx+29h], 5
0x140068814  jnb     short loc_14006881C
0x140068816  cmp     [rcx+48h], bp
0x14006881a  jz      short loc_140068836
0x14006881c  mov     rcx, [rcx+40h]
0x140068820  mov     r9d, 0Bh
0x140068826  mov     dl, 5
0x140068828  mov     [rsp+68h+var_48], r12
0x14006882d  lea     r8d, [r9-0Ah]
0x140068831  call    WPP_RECORDER_SF_
0x140068836  mov     edx, 18h
0x14006883b  mov     r8d, 47696457h
0x140068841  lea     ecx, [rdx+28h]
0x140068844  call    cs:__imp_ExAllocatePool2
0x14006884b  nop     dword ptr [rax+rax+00h]
0x140068850  mov     rdi, rax
0x140068853  test    rax, rax
0x140068856  jz      short loc_140068872
0x140068858  mov     rcx, rax; SpinLock
0x14006885b  mov     [rax+10h], bpl
0x14006885f  call    cs:__imp_KeInitializeSpinLock
0x140068866  nop     dword ptr [rax+rax+00h]
0x14006886b  mov     ebx, ebp
0x14006886d  mov     [rsi], rdi
0x140068870  jmp     short loc_140068877
0x140068872  mov     ebx, 0C000009Ah
0x140068877  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14006887e  jz      short loc_1400688B1
0x140068880  mov     rcx, cs:WPP_GLOBAL_Control
0x140068887  cmp     byte ptr [rcx+29h], 5
0x14006888b  jnb     short loc_140068893
0x14006888d  cmp     [rcx+48h], bp
0x140068891  jz      short loc_1400688B1
0x140068893  mov     rcx, [rcx+40h]
0x140068897  mov     r9d, 0Ch
0x14006889d  mov     [rsp+68h+var_40], ebx
0x1400688a1  mov     dl, 5
0x1400688a3  mov     [rsp+68h+var_48], r12
0x1400688a8  lea     r8d, [r9-0Bh]
0x1400688ac  call    WPP_RECORDER_SF_D
0x1400688b1  mov     eax, ebx
0x1400688b3  add     rsp, 38h
0x1400688b7  pop     r14
0x1400688b9  pop     r12
0x1400688bb  pop     rdi
0x1400688bc  pop     rsi
0x1400688bd  pop     rbp
0x1400688be  pop     rbx
0x1400688bf  retn
```
