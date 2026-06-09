# Apx::ApfIpcIoLink::~ApfIpcIoLink(void)

- ea: `0x180027520`
- end: `0x18002763a`
- name: `??1ApfIpcIoLink@Apx@@EEAA@XZ`
- size: `282`
- prototype: `void __fastcall(Apx::ApfIpcIoLink *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180027660`

## callees

- `0x18000a12c`
- `0x18000c690`
- `0x18000d2f0`
- `0x180027520`
- `0x180028010`
- `0x18002963c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800275a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800275c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800275a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800275c0`

## string_xrefs

- `0x18002757a`: `onecoreuap\drivers\wdm\audio\backpln\apx\class\ipclinks\apfipciolink.cpp`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink::~ApfIpcIoLink(Apx::ApfIpcIoLink *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &Apx::ApfIpcIoLink::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
  Apx::ApfIpcIoLink::Deinitialize(this);
  imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~*((_QWORD *)this + 13));
  v2 = (void *)*((_QWORD *)this + 52);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 52) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 53);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 53) = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
  *((_QWORD *)this + 48) = &Apx::ApfWorkItemBase::`vftable';
  Apx::ApfWorkItemQueue::~ApfWorkItemQueue((Apx::ApfIpcIoLink *)((char *)this + 264));
  *((_QWORD *)this + 30) = &Apx::ApfWorkItemBase::`vftable';
  Apx::ApfWorkItemQueue::~ApfWorkItemQueue((Apx::ApfIpcIoLink *)((char *)this + 120));
  Apx::ApfIpcLink::~ApfIpcLink(this);
}

```

## disassembly

```asm
0x180027520  mov     [rsp+arg_0], rbx
0x180027525  push    rdi
0x180027526  sub     rsp, 30h
0x18002752a  mov     rbx, rcx
0x18002752d  lea     rax, ??_7ApfIpcIoLink@Apx@@6B@; const Apx::ApfIpcIoLink::`vftable'
0x180027534  mov     [rcx], rax
0x180027537  lea     rdi, WPP_GLOBAL_Control
0x18002753e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027545  cmp     rcx, rdi
0x180027548  jz      short loc_18002756B
0x18002754a  test    byte ptr [rcx+1Ch], 1
0x18002754e  jz      short loc_18002756B
0x180027550  cmp     byte ptr [rcx+19h], 5
0x180027554  jb      short loc_18002756B
0x180027556  mov     edx, 0Fh
0x18002755b  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180027562  mov     rcx, [rcx+10h]
0x180027566  call    WPP_SF_
0x18002756b  mov     rcx, rbx; this
0x18002756e  call    ?Deinitialize@ApfIpcIoLink@Apx@@EEAAXXZ; Apx::ApfIpcIoLink::Deinitialize(void)
0x180027573  mov     rdx, [rbx+68h]
0x180027577  not     rdx; Apx::ApfVerify *
0x18002757a  lea     rax, aOnecoreuapDriv_1; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180027581  mov     [rsp+38h+var_18], rax
0x180027586  xor     ecx, ecx; this
0x180027588  lea     r9d, [rcx+65h]
0x18002758c  mov     r8d, 44787041h
0x180027592  call    imp_ApxObjectDereferenceActual
0x180027597  mov     rcx, [rbx+1A0h]; hObject
0x18002759e  test    rcx, rcx
0x1800275a1  jz      short loc_1800275B4
0x1800275a3  call    cs:__imp_CloseHandle
0x1800275a9  mov     qword ptr [rbx+1A0h], 0
0x1800275b4  mov     rcx, [rbx+1A8h]; hObject
0x1800275bb  test    rcx, rcx
0x1800275be  jz      short loc_1800275D1
0x1800275c0  call    cs:__imp_CloseHandle
0x1800275c6  mov     qword ptr [rbx+1A8h], 0
0x1800275d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275d8  cmp     rcx, rdi
0x1800275db  jz      short loc_1800275FE
0x1800275dd  test    byte ptr [rcx+1Ch], 1
0x1800275e1  jz      short loc_1800275FE
0x1800275e3  cmp     byte ptr [rcx+19h], 5
0x1800275e7  jb      short loc_1800275FE
0x1800275e9  mov     edx, 10h
0x1800275ee  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x1800275f5  mov     rcx, [rcx+10h]
0x1800275f9  call    WPP_SF_
0x1800275fe  lea     rdi, ??_7ApfWorkItemBase@Apx@@6B@; const Apx::ApfWorkItemBase::`vftable'
0x180027605  mov     [rbx+180h], rdi
0x18002760c  lea     rcx, [rbx+108h]; this
0x180027613  call    ??1ApfWorkItemQueue@Apx@@UEAA@XZ; Apx::ApfWorkItemQueue::~ApfWorkItemQueue(void)
0x180027618  mov     [rbx+0F0h], rdi
0x18002761f  lea     rcx, [rbx+78h]; this
0x180027623  call    ??1ApfWorkItemQueue@Apx@@UEAA@XZ; Apx::ApfWorkItemQueue::~ApfWorkItemQueue(void)
0x180027628  mov     rcx, rbx; this
0x18002762b  mov     rbx, [rsp+38h+arg_0]
0x180027630  add     rsp, 30h
0x180027634  pop     rdi
0x180027635  jmp     ??1ApfIpcLink@Apx@@MEAA@XZ; Apx::ApfIpcLink::~ApfIpcLink(void)
```
