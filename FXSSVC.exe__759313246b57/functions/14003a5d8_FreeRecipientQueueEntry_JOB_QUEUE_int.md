# FreeRecipientQueueEntry(_JOB_QUEUE *,int)

- ea: `0x14003a5d8`
- end: `0x14003a754`
- name: `?FreeRecipientQueueEntry@@YAXPEAU_JOB_QUEUE@@H@Z`
- size: `380`
- prototype: `void __fastcall(struct _JOB_QUEUE *this, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140038090`
- `0x14003da4c`
- `0x140049678`

## callees

- `0x140001bac`
- `0x140004c78`
- `0x14003a5d8`
- `0x14003c4ac`
- `0x14006998c`
- `0x1400798f0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14003a6fe`
- `KERNEL32!DeleteCriticalSection` at `0x14003a711`
- `KERNEL32!DeleteCriticalSection` at `0x14003a724`
- `KERNEL32!DeleteCriticalSection` at `0x14003a6fe`
- `KERNEL32!DeleteCriticalSection` at `0x14003a711`
- `KERNEL32!DeleteCriticalSection` at `0x14003a724`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FreeRecipientQueueEntry(struct _JOB_QUEUE *this)
{
  CMapDeviceId *v2; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 && *((_BYTE *)v2 + 25) >= 5u )
      WPP_SF_(*((_QWORD *)v2 + 2), 228, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  pMemFree(*((LPVOID *)this + 14));
  pMemFree(*((LPVOID *)this + 20));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  FreePersonalProfile((char *)this + 240);
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  FreePersonalProfile((char *)this + 448);
  pMemFree(*((LPVOID *)this + 9));
  pMemFree(*((LPVOID *)this + 50));
  pMemFree(*((LPVOID *)this + 7));
  pMemFree(*((LPVOID *)this + 75));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 43);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1776));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  if ( *((_DWORD *)this + 9) != 32 )
    _JOB_QUEUE::PutStatus(this, 0);
  operator delete(this);
}

```

## disassembly

```asm
0x14003a5d8  mov     [rsp+arg_0], rbx
0x14003a5dd  push    rbp
0x14003a5de  sub     rsp, 20h
0x14003a5e2  mov     rbx, rcx
0x14003a5e5  lea     rbp, WPP_GLOBAL_Control
0x14003a5ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a5f3  cmp     rcx, rbp
0x14003a5f6  jz      short loc_14003A646
0x14003a5f8  test    byte ptr [rcx+1Ch], 4
0x14003a5fc  jz      short loc_14003A620
0x14003a5fe  cmp     byte ptr [rcx+19h], 5
0x14003a602  jb      short loc_14003A620
0x14003a604  mov     edx, 0E3h
0x14003a609  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a610  mov     rcx, [rcx+10h]
0x14003a614  call    WPP_SF_
0x14003a619  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a620  cmp     rcx, rbp
0x14003a623  jz      short loc_14003A646
0x14003a625  test    byte ptr [rcx+1Ch], 4
0x14003a629  jz      short loc_14003A646
0x14003a62b  cmp     byte ptr [rcx+19h], 5
0x14003a62f  jb      short loc_14003A646
0x14003a631  mov     edx, 0E4h
0x14003a636  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a63d  mov     rcx, [rcx+10h]
0x14003a641  call    WPP_SF_
0x14003a646  mov     rcx, [rbx+70h]; lpMem
0x14003a64a  call    pMemFree
0x14003a64f  mov     rcx, [rbx+0A0h]; lpMem
0x14003a656  call    pMemFree
0x14003a65b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a662  cmp     rcx, rbp
0x14003a665  jz      short loc_14003A688
0x14003a667  test    byte ptr [rcx+1Ch], 4
0x14003a66b  jz      short loc_14003A688
0x14003a66d  cmp     byte ptr [rcx+19h], 5
0x14003a671  jb      short loc_14003A688
0x14003a673  mov     edx, 0E5h
0x14003a678  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a67f  mov     rcx, [rcx+10h]
0x14003a683  call    WPP_SF_
0x14003a688  lea     rcx, [rbx+0F0h]
0x14003a68f  call    FreePersonalProfile
0x14003a694  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a69b  cmp     rcx, rbp
0x14003a69e  jz      short loc_14003A6C1
0x14003a6a0  test    byte ptr [rcx+1Ch], 4
0x14003a6a4  jz      short loc_14003A6C1
0x14003a6a6  cmp     byte ptr [rcx+19h], 5
0x14003a6aa  jb      short loc_14003A6C1
0x14003a6ac  mov     edx, 0E6h
0x14003a6b1  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003a6b8  mov     rcx, [rcx+10h]
0x14003a6bc  call    WPP_SF_
0x14003a6c1  lea     rcx, [rbx+1C0h]
0x14003a6c8  call    FreePersonalProfile
0x14003a6cd  mov     rcx, [rbx+48h]; lpMem
0x14003a6d1  call    pMemFree
0x14003a6d6  mov     rcx, [rbx+190h]; lpMem
0x14003a6dd  call    pMemFree
0x14003a6e2  mov     rcx, [rbx+38h]; lpMem
0x14003a6e6  call    pMemFree
0x14003a6eb  mov     rcx, [rbx+258h]; lpMem
0x14003a6f2  call    pMemFree
0x14003a6f7  lea     rcx, [rbx+6B8h]; lpCriticalSection
0x14003a6fe  call    cs:__imp_DeleteCriticalSection
0x14003a705  nop     dword ptr [rax+rax+00h]
0x14003a70a  lea     rcx, [rbx+6F0h]; lpCriticalSection
0x14003a711  call    cs:__imp_DeleteCriticalSection
0x14003a718  nop     dword ptr [rax+rax+00h]
0x14003a71d  lea     rcx, [rbx+260h]; lpCriticalSection
0x14003a724  call    cs:__imp_DeleteCriticalSection
0x14003a72b  nop     dword ptr [rax+rax+00h]
0x14003a730  nop
0x14003a731  cmp     dword ptr [rbx+24h], 20h ; ' '
0x14003a735  jz      short loc_14003A742
0x14003a737  xor     edx, edx; unsigned int
0x14003a739  mov     rcx, rbx; this
0x14003a73c  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x14003a741  nop
0x14003a742  mov     rcx, rbx; Block
0x14003a745  mov     rbx, [rsp+28h+arg_0]
0x14003a74a  add     rsp, 20h
0x14003a74e  pop     rbp
0x14003a74f  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
