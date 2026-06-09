# Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)

- ea: `0x180009660`
- end: `0x180009701`
- name: `??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `161`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CCvDDCache::CCvDD *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800093c0`
- `0x180009704`
- `0x180009e74`
- `0x18000d420`
- `0x180027e2e`
- `0x180027e6d`

## callees

- `0x180009660`
- `0x1800268f4`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(
        Microsoft::Windows::Performance::CCvDDCache::CCvDD *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 15);
  if ( v2 )
    operator delete(v2);
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  operator delete(*((void **)this + 13));
  *((_QWORD *)this + 13) = 0;
  operator delete(*((void **)this + 12));
  *((_QWORD *)this + 12) = 0;
  operator delete(*((void **)this + 11));
  *((_QWORD *)this + 11) = 0;
  if ( *((_QWORD *)this + 9) >= 8u )
    operator delete(*((void **)this + 6));
  *((_QWORD *)this + 9) = 7;
  *((_QWORD *)this + 8) = 0;
  *((_WORD *)this + 24) = 0;
  if ( *((_QWORD *)this + 4) >= 8u )
    operator delete(*((void **)this + 1));
  *((_QWORD *)this + 4) = 7;
  *((_QWORD *)this + 3) = 0;
  *((_WORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x180009660  mov     [rsp+arg_0], rbx
0x180009665  push    rdi
0x180009666  sub     rsp, 20h
0x18000966a  mov     rbx, rcx
0x18000966d  xor     edi, edi
0x18000966f  mov     rcx, [rcx+78h]; Block
0x180009673  test    rcx, rcx
0x180009676  jz      short loc_18000967D
0x180009678  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000967d  mov     [rbx+78h], rdi
0x180009681  mov     [rbx+80h], rdi
0x180009688  mov     [rbx+88h], rdi
0x18000968f  mov     rcx, [rbx+68h]; Block
0x180009693  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009698  mov     [rbx+68h], rdi
0x18000969c  mov     rcx, [rbx+60h]; Block
0x1800096a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800096a5  mov     [rbx+60h], rdi
0x1800096a9  mov     rcx, [rbx+58h]; Block
0x1800096ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800096b2  mov     [rbx+58h], rdi
0x1800096b6  cmp     qword ptr [rbx+48h], 8
0x1800096bb  jb      short loc_1800096C6
0x1800096bd  mov     rcx, [rbx+30h]; Block
0x1800096c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800096c6  mov     qword ptr [rbx+48h], 7
0x1800096ce  mov     [rbx+40h], rdi
0x1800096d2  mov     [rbx+30h], di
0x1800096d6  cmp     qword ptr [rbx+20h], 8
0x1800096db  jb      short loc_1800096E6
0x1800096dd  mov     rcx, [rbx+8]; Block
0x1800096e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800096e6  mov     qword ptr [rbx+20h], 7
0x1800096ee  mov     [rbx+18h], rdi
0x1800096f2  mov     [rbx+8], di
0x1800096f6  mov     rbx, [rsp+28h+arg_0]
0x1800096fb  add     rsp, 20h
0x1800096ff  pop     rdi
0x180009700  retn
```
