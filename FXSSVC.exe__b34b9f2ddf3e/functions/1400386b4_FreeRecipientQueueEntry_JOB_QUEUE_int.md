# FreeRecipientQueueEntry(_JOB_QUEUE *,int)

- ea: `0x1400386b4`
- end: `0x14003881e`
- name: `?FreeRecipientQueueEntry@@YAXPEAU_JOB_QUEUE@@H@Z`
- size: `362`
- prototype: `void __fastcall(struct _JOB_QUEUE *this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1400362a0`
- `0x14003b880`
- `0x140046a7c`

## callees

- `0x140001b8c`
- `0x140004b30`
- `0x1400386b4`
- `0x14003a3d8`
- `0x140065dbc`
- `0x140074d4c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400387da`
- `KERNEL32!DeleteCriticalSection` at `0x1400387e7`
- `KERNEL32!DeleteCriticalSection` at `0x1400387f4`
- `KERNEL32!DeleteCriticalSection` at `0x1400387da`
- `KERNEL32!DeleteCriticalSection` at `0x1400387e7`
- `KERNEL32!DeleteCriticalSection` at `0x1400387f4`

## pseudocode

```c
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
0x1400386b4  mov     [rsp+arg_0], rbx
0x1400386b9  push    rbp
0x1400386ba  sub     rsp, 20h
0x1400386be  mov     rbx, rcx
0x1400386c1  lea     rbp, WPP_GLOBAL_Control
0x1400386c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400386cf  cmp     rcx, rbp
0x1400386d2  jz      short loc_140038722
0x1400386d4  test    byte ptr [rcx+1Ch], 4
0x1400386d8  jz      short loc_1400386FC
0x1400386da  cmp     byte ptr [rcx+19h], 5
0x1400386de  jb      short loc_1400386FC
0x1400386e0  mov     edx, 0E3h
0x1400386e5  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x1400386ec  mov     rcx, [rcx+10h]
0x1400386f0  call    WPP_SF_
0x1400386f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400386fc  cmp     rcx, rbp
0x1400386ff  jz      short loc_140038722
0x140038701  test    byte ptr [rcx+1Ch], 4
0x140038705  jz      short loc_140038722
0x140038707  cmp     byte ptr [rcx+19h], 5
0x14003870b  jb      short loc_140038722
0x14003870d  mov     edx, 0E4h
0x140038712  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038719  mov     rcx, [rcx+10h]
0x14003871d  call    WPP_SF_
0x140038722  mov     rcx, [rbx+70h]; lpMem
0x140038726  call    pMemFree
0x14003872b  mov     rcx, [rbx+0A0h]; lpMem
0x140038732  call    pMemFree
0x140038737  mov     rcx, cs:WPP_GLOBAL_Control
0x14003873e  cmp     rcx, rbp
0x140038741  jz      short loc_140038764
0x140038743  test    byte ptr [rcx+1Ch], 4
0x140038747  jz      short loc_140038764
0x140038749  cmp     byte ptr [rcx+19h], 5
0x14003874d  jb      short loc_140038764
0x14003874f  mov     edx, 0E5h
0x140038754  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003875b  mov     rcx, [rcx+10h]
0x14003875f  call    WPP_SF_
0x140038764  lea     rcx, [rbx+0F0h]
0x14003876b  call    FreePersonalProfile
0x140038770  mov     rcx, cs:WPP_GLOBAL_Control
0x140038777  cmp     rcx, rbp
0x14003877a  jz      short loc_14003879D
0x14003877c  test    byte ptr [rcx+1Ch], 4
0x140038780  jz      short loc_14003879D
0x140038782  cmp     byte ptr [rcx+19h], 5
0x140038786  jb      short loc_14003879D
0x140038788  mov     edx, 0E6h
0x14003878d  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038794  mov     rcx, [rcx+10h]
0x140038798  call    WPP_SF_
0x14003879d  lea     rcx, [rbx+1C0h]
0x1400387a4  call    FreePersonalProfile
0x1400387a9  mov     rcx, [rbx+48h]; lpMem
0x1400387ad  call    pMemFree
0x1400387b2  mov     rcx, [rbx+190h]; lpMem
0x1400387b9  call    pMemFree
0x1400387be  mov     rcx, [rbx+38h]; lpMem
0x1400387c2  call    pMemFree
0x1400387c7  mov     rcx, [rbx+258h]; lpMem
0x1400387ce  call    pMemFree
0x1400387d3  lea     rcx, [rbx+6B8h]; lpCriticalSection
0x1400387da  call    cs:__imp_DeleteCriticalSection
0x1400387e0  lea     rcx, [rbx+6F0h]; lpCriticalSection
0x1400387e7  call    cs:__imp_DeleteCriticalSection
0x1400387ed  lea     rcx, [rbx+260h]; lpCriticalSection
0x1400387f4  call    cs:__imp_DeleteCriticalSection
0x1400387fa  nop
0x1400387fb  cmp     dword ptr [rbx+24h], 20h ; ' '
0x1400387ff  jz      short loc_14003880C
0x140038801  xor     edx, edx; unsigned int
0x140038803  mov     rcx, rbx; this
0x140038806  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x14003880b  nop
0x14003880c  mov     rcx, rbx; Block
0x14003880f  mov     rbx, [rsp+28h+arg_0]
0x140038814  add     rsp, 20h
0x140038818  pop     rbp
0x140038819  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
