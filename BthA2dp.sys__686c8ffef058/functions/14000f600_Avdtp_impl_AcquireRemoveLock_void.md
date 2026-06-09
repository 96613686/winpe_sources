# Avdtp_impl::AcquireRemoveLock(void)

- ea: `0x14000f600`
- end: `0x14000f6db`
- name: `?AcquireRemoveLock@Avdtp_impl@@QEAAJXZ`
- size: `219`
- prototype: `__int64 __fastcall(Avdtp_impl *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400132a0`
- `0x140019718`
- `0x1400473d0`
- `0x14004891c`

## callees

- `0x14000f600`
- `0x14000f6e4`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000f634`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000f634`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::AcquireRemoveLock(Avdtp_impl *this)
{
  struct _IO_REMOVE_LOCK *v2; // rcx
  int v3; // edx
  unsigned int v4; // edi
  int v5; // r8d

  v2 = (struct _IO_REMOVE_LOCK *)*((_QWORD *)this + 224);
  if ( !v2 )
    return 0;
  v4 = IoAcquireRemoveLockEx(
         v2,
         (PVOID)0x41564454,
         "onecoreuap\\drivers\\wdm\\audio\\drivers\\bluetooth\\btha2dp\\avdtp\\driver\\avdtp_impl.cpp",
         0x209u,
         0x20u);
  LOBYTE(v3) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_llq(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      v5,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      16,
      (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
      v4,
      *(_DWORD *)(*((_QWORD *)this + 224) + 4LL),
      (char)this);
  }
  return v4;
}

```

## disassembly

```asm
0x14000f600  push    rbx
0x14000f602  sub     rsp, 60h
0x14000f606  mov     rbx, rcx
0x14000f609  mov     rcx, [rcx+700h]; RemoveLock
0x14000f610  test    rcx, rcx
0x14000f613  jz      short loc_14000F691
0x14000f615  mov     r9d, 209h; Line
0x14000f61b  mov     [rsp+68h+arg_0], rdi
0x14000f620  lea     r8, File; "onecoreuap\\drivers\\wdm\\audio\\driver"...
0x14000f627  mov     [rsp+68h+RemlockSize], 20h ; ' '; RemlockSize
0x14000f62f  mov     edx, 41564454h; Tag
0x14000f634  call    cs:__imp_IoAcquireRemoveLockEx
0x14000f63b  nop     dword ptr [rax+rax+00h]
0x14000f640  mov     edi, eax
0x14000f642  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f649  lea     rax, WPP_GLOBAL_Control
0x14000f650  cmp     rcx, rax
0x14000f653  jnz     short loc_14000F680
0x14000f655  xor     dl, dl
0x14000f657  lea     rax, WPP_RECORDER_INITIALIZED
0x14000f65e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000f665  setnz   r8b
0x14000f669  test    dl, dl
0x14000f66b  jnz     short loc_14000F695
0x14000f66d  test    r8b, r8b
0x14000f670  jnz     short loc_14000F695
0x14000f672  mov     eax, edi
0x14000f674  mov     rdi, [rsp+68h+arg_0]
0x14000f679  add     rsp, 60h
0x14000f67d  pop     rbx
0x14000f67e  retn
0x14000f680  mov     eax, [rcx+2Ch]
0x14000f683  test    al, 8
0x14000f685  jz      short loc_14000F655
0x14000f687  cmp     byte ptr [rcx+29h], 4
0x14000f68b  jb      short loc_14000F655
0x14000f68d  mov     dl, 1
0x14000f68f  jmp     short loc_14000F657
0x14000f691  xor     eax, eax
0x14000f693  jmp     short loc_14000F679
0x14000f695  mov     rax, [rbx+700h]
0x14000f69c  mov     r9, [rcx+40h]
0x14000f6a0  mov     rcx, [rcx+18h]
0x14000f6a4  mov     [rsp+68h+var_18], rbx
0x14000f6a9  mov     eax, [rax+4]
0x14000f6ac  mov     [rsp+68h+var_20], eax
0x14000f6b0  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14000f6b7  mov     [rsp+68h+var_28], edi
0x14000f6bb  mov     [rsp+68h+var_30], rax
0x14000f6c0  mov     [rsp+68h+var_38], 10h
0x14000f6c7  mov     [rsp+68h+var_40], 4
0x14000f6cf  mov     byte ptr [rsp+68h+RemlockSize], 4
0x14000f6d4  call    WPP_RECORDER_AND_TRACE_SF_llq
0x14000f6d9  jmp     short loc_14000F672
```
