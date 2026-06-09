# CASFDataUnitExtensionObject::SetExtensionSystemInfo(ulong,uchar *)

- ea: `0x180017260`
- end: `0x18001730c`
- name: `?SetExtensionSystemInfo@CASFDataUnitExtensionObject@@UEAAJKPEAE@Z`
- size: `172`
- prototype: `int(CASFDataUnitExtensionObject *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800021dc`
- `0x18000220c`
- `0x180017260`
- `0x18003f2a0`

## pseudocode

```c
__int64 __fastcall CASFDataUnitExtensionObject::SetExtensionSystemInfo(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3)
{
  unsigned __int64 v3; // rbx
  unsigned int v6; // ebx
  struct IWMSCriticalSection *v7; // rsi
  struct IWMSCriticalSection *v8; // rax
  struct IWMSCriticalSection *v9; // rcx
  char v11; // [rsp+40h] [rbp+8h] BYREF

  v3 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v11, this[4]);
  if ( this[5] )
  {
    if ( a3 || !(_DWORD)v3 )
    {
      v7 = 0;
      if ( a3 && (_DWORD)v3 )
      {
        v8 = (struct IWMSCriticalSection *)operator new[](v3);
        v7 = v8;
        if ( !v8 )
        {
          v6 = -2147024882;
          goto LABEL_14;
        }
        memcpy_0(v8, a3, v3);
      }
      v9 = this[14];
      if ( v9 )
        operator delete(v9);
      *((_DWORD *)this + 26) = v3;
      v6 = 0;
      this[14] = v7;
    }
    else
    {
      v6 = -2147024809;
    }
  }
  else
  {
    v6 = -1072887818;
  }
LABEL_14:
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v11);
  return v6;
}

```

## disassembly

```asm
0x180017260  mov     [rsp+arg_8], rbx
0x180017265  mov     [rsp+arg_10], rbp
0x18001726a  push    rsi
0x18001726b  push    rdi
0x18001726c  push    r14
0x18001726e  sub     rsp, 20h
0x180017272  mov     ebx, edx
0x180017274  mov     rdi, rcx
0x180017277  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18001727b  mov     rbp, r8
0x18001727e  lea     rcx, [rsp+38h+arg_0]; this
0x180017283  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180017288  cmp     qword ptr [rdi+28h], 0
0x18001728d  jnz     short loc_180017296
0x18001728f  mov     ebx, 0C00D07F6h
0x180017294  jmp     short loc_1800172ED
0x180017296  test    rbp, rbp
0x180017299  jnz     short loc_1800172A6
0x18001729b  test    ebx, ebx
0x18001729d  jz      short loc_1800172A6
0x18001729f  mov     ebx, 80070057h
0x1800172a4  jmp     short loc_1800172ED
0x1800172a6  xor     esi, esi
0x1800172a8  test    rbp, rbp
0x1800172ab  jz      short loc_1800172D6
0x1800172ad  test    ebx, ebx
0x1800172af  jz      short loc_1800172D6
0x1800172b1  mov     rcx, rbx; unsigned __int64
0x1800172b4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800172b9  mov     rsi, rax
0x1800172bc  test    rax, rax
0x1800172bf  jnz     short loc_1800172C8
0x1800172c1  mov     ebx, 8007000Eh
0x1800172c6  jmp     short loc_1800172ED
0x1800172c8  mov     r8, rbx; Size
0x1800172cb  mov     rdx, rbp; Src
0x1800172ce  mov     rcx, rax; void *
0x1800172d1  call    memcpy_0
0x1800172d6  mov     rcx, [rdi+70h]; Block
0x1800172da  test    rcx, rcx
0x1800172dd  jz      short loc_1800172E4
0x1800172df  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800172e4  mov     [rdi+68h], ebx
0x1800172e7  xor     ebx, ebx
0x1800172e9  mov     [rdi+70h], rsi
0x1800172ed  lea     rcx, [rsp+38h+arg_0]; this
0x1800172f2  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800172f7  mov     rbp, [rsp+38h+arg_10]
0x1800172fc  mov     eax, ebx
0x1800172fe  mov     rbx, [rsp+38h+arg_8]
0x180017303  add     rsp, 20h
0x180017307  pop     r14
0x180017309  pop     rdi
0x18001730a  pop     rsi
0x18001730b  retn
```
