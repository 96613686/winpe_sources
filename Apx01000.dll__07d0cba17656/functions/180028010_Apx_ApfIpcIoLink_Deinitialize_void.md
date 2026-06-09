# Apx::ApfIpcIoLink::Deinitialize(void)

- ea: `0x180028010`
- end: `0x180028112`
- name: `?Deinitialize@ApfIpcIoLink@Apx@@EEAAXXZ`
- size: `258`
- prototype: `void __fastcall(unsigned __int64 this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180027520`

## callees

- `0x180002100`
- `0x18000a12c`
- `0x18000c938`
- `0x180027204`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800280ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800280ab`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink::Deinitialize(unsigned __int64 this)
{
  _QWORD *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 && *((_BYTE *)v2 + 25) >= 4u )
      WPP_SF_qi(v2[2], 25, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids, ~this, *(_QWORD *)(this + 64));
  }
  Apx::ApfWorkItemQueue::Deinitialize((Apx::ApfWorkItemQueue *)(this + 264));
  Apx::ApfWorkItemQueue::Deinitialize((Apx::ApfWorkItemQueue *)(this + 120));
  v3 = *(void **)(this + 112);
  if ( v3 )
  {
    CloseHandle(v3);
    *(_QWORD *)(this + 112) = 0;
  }
  v4 = *(void **)(this + 256);
  if ( v4 )
  {
    operator delete(v4, (const struct std::nothrow_t *)0x318);
    *(_QWORD *)(this + 256) = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
}

```

## disassembly

```asm
0x180028010  mov     [rsp+arg_0], rbx
0x180028015  push    rdi
0x180028016  sub     rsp, 30h
0x18002801a  mov     rbx, rcx
0x18002801d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028024  lea     rdi, WPP_GLOBAL_Control
0x18002802b  cmp     rcx, rdi
0x18002802e  jz      short loc_18002808D
0x180028030  test    byte ptr [rcx+1Ch], 1
0x180028034  jz      short loc_180028058
0x180028036  cmp     byte ptr [rcx+19h], 5
0x18002803a  jb      short loc_180028058
0x18002803c  mov     rcx, [rcx+10h]
0x180028040  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028047  mov     edx, 18h
0x18002804c  call    WPP_SF_
0x180028051  mov     rcx, cs:WPP_GLOBAL_Control
0x180028058  cmp     rcx, rdi
0x18002805b  jz      short loc_18002808D
0x18002805d  test    byte ptr [rcx+1Ch], 20h
0x180028061  jz      short loc_18002808D
0x180028063  cmp     byte ptr [rcx+19h], 4
0x180028067  jb      short loc_18002808D
0x180028069  mov     rax, [rbx+40h]
0x18002806d  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180028074  mov     rcx, [rcx+10h]
0x180028078  mov     r9, rbx
0x18002807b  not     r9
0x18002807e  mov     [rsp+38h+var_18], rax
0x180028083  mov     edx, 19h
0x180028088  call    WPP_SF_qi
0x18002808d  lea     rcx, [rbx+108h]; this
0x180028094  call    ?Deinitialize@ApfWorkItemQueue@Apx@@QEAAXXZ; Apx::ApfWorkItemQueue::Deinitialize(void)
0x180028099  lea     rcx, [rbx+78h]; this
0x18002809d  call    ?Deinitialize@ApfWorkItemQueue@Apx@@QEAAXXZ; Apx::ApfWorkItemQueue::Deinitialize(void)
0x1800280a2  mov     rcx, [rbx+70h]; hObject
0x1800280a6  test    rcx, rcx
0x1800280a9  jz      short loc_1800280B9
0x1800280ab  call    cs:__imp_CloseHandle
0x1800280b1  mov     qword ptr [rbx+70h], 0
0x1800280b9  mov     rcx, [rbx+100h]; void *
0x1800280c0  test    rcx, rcx
0x1800280c3  jz      short loc_1800280DA
0x1800280c5  mov     edx, 318h; struct std::nothrow_t *
0x1800280ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800280cf  mov     qword ptr [rbx+100h], 0
0x1800280da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280e1  cmp     rcx, rdi
0x1800280e4  jz      short loc_180028107
0x1800280e6  test    byte ptr [rcx+1Ch], 1
0x1800280ea  jz      short loc_180028107
0x1800280ec  cmp     byte ptr [rcx+19h], 5
0x1800280f0  jb      short loc_180028107
0x1800280f2  mov     rcx, [rcx+10h]
0x1800280f6  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x1800280fd  mov     edx, 1Ah
0x180028102  call    WPP_SF_
0x180028107  mov     rbx, [rsp+38h+arg_0]
0x18002810c  add     rsp, 30h
0x180028110  pop     rdi
0x180028111  retn
```
