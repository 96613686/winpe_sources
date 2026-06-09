# Apx::ApfIpcIoLink::Start(void)

- ea: `0x180029040`
- end: `0x180029111`
- name: `?Start@ApfIpcIoLink@Apx@@UEAAXXZ`
- size: `209`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000a12c`
- `0x18000a1b4`
- `0x18000c7ec`
- `0x180029040`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029088`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029088`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink::Start(HANDLE *this)
{
  _QWORD *v2; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
  ResetEvent(this[52]);
  *((_BYTE *)this + 432) = 0;
  if ( (int)Apx::ApfWorkItemQueue::AddWorkItemToQueue(
              (Apx::ApfWorkItemQueue *)(this + 15),
              (struct Apx::ApfWorkItemBase *)(this + 30)) >= 0 )
    goto LABEL_10;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
LABEL_10:
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_(v2[2], 29, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
}

```

## disassembly

```asm
0x180029040  mov     [rsp+arg_0], rbx
0x180029045  push    rdi
0x180029046  sub     rsp, 20h
0x18002904a  mov     rbx, rcx
0x18002904d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029054  lea     rdi, WPP_GLOBAL_Control
0x18002905b  cmp     rcx, rdi
0x18002905e  jz      short loc_180029081
0x180029060  test    byte ptr [rcx+1Ch], 1
0x180029064  jz      short loc_180029081
0x180029066  cmp     byte ptr [rcx+19h], 5
0x18002906a  jb      short loc_180029081
0x18002906c  mov     rcx, [rcx+10h]
0x180029070  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180029077  mov     edx, 1Bh
0x18002907c  call    WPP_SF_
0x180029081  mov     rcx, [rbx+1A0h]; hEvent
0x180029088  call    cs:__imp_ResetEvent
0x18002908e  lea     rdx, [rbx+0F0h]; struct Apx::ApfWorkItemBase *
0x180029095  mov     byte ptr [rbx+1B0h], 0
0x18002909c  lea     rcx, [rbx+78h]; this
0x1800290a0  call    ?AddWorkItemToQueue@ApfWorkItemQueue@Apx@@QEAAJPEAVApfWorkItemBase@2@@Z; Apx::ApfWorkItemQueue::AddWorkItemToQueue(Apx::ApfWorkItemBase *)
0x1800290a5  test    eax, eax
0x1800290a7  jns     short loc_1800290D9
0x1800290a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290b0  cmp     rcx, rdi
0x1800290b3  jz      short loc_180029106
0x1800290b5  test    byte ptr [rcx+1Ch], 80h
0x1800290b9  jz      short loc_1800290E0
0x1800290bb  cmp     byte ptr [rcx+19h], 3
0x1800290bf  jb      short loc_1800290E0
0x1800290c1  mov     rcx, [rcx+10h]
0x1800290c5  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x1800290cc  mov     edx, 1Ch
0x1800290d1  mov     r9d, eax
0x1800290d4  call    WPP_SF_d
0x1800290d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290e0  cmp     rcx, rdi
0x1800290e3  jz      short loc_180029106
0x1800290e5  test    byte ptr [rcx+1Ch], 1
0x1800290e9  jz      short loc_180029106
0x1800290eb  cmp     byte ptr [rcx+19h], 5
0x1800290ef  jb      short loc_180029106
0x1800290f1  mov     rcx, [rcx+10h]
0x1800290f5  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x1800290fc  mov     edx, 1Dh
0x180029101  call    WPP_SF_
0x180029106  mov     rbx, [rsp+28h+arg_0]
0x18002910b  add     rsp, 20h
0x18002910f  pop     rdi
0x180029110  retn
```
