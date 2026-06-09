# JDictsFileMapping::OpenFile(ushort const *,int,unsigned __int64)

- ea: `0x18001fae0`
- end: `0x18001fbc0`
- name: `?OpenFile@JDictsFileMapping@@UEAAJPEBGH_K@Z`
- size: `224`
- prototype: `__int64 __fastcall(JDictsFileMapping *this, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001a30`
- `0x18001fae0`
- `0x180020810`
- `0x180020d5c`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001fb4a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fb9d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fb4a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fb9d`

## pseudocode

```c
__int64 __fastcall JDictsFileMapping::OpenFile(JDictsFileMapping *this, unsigned __int16 *a2, int a3)
{
  CommonFileMapping *v7; // rax
  CommonFileMapping *v8; // rbx
  CommonFileMapping *v9; // rsi
  __int64 v10; // rcx
  void *v11; // rbx

  if ( *((_DWORD *)this + 4) )
    return 2147943647LL;
  v7 = (CommonFileMapping *)operator new(0x30u);
  if ( v7 )
    v8 = CommonFileMapping::CommonFileMapping(v7, a2, a3);
  else
    v8 = 0;
  v9 = (CommonFileMapping *)*((_QWORD *)this + 1);
  if ( v8 == v9 )
  {
    v8 = (CommonFileMapping *)*((_QWORD *)this + 1);
  }
  else
  {
    if ( v9 )
    {
      CommonFileMapping::~CommonFileMapping(*((CommonFileMapping **)this + 1));
      operator delete(v9);
    }
    *((_QWORD *)this + 1) = v8;
  }
  if ( !v8 )
    return 2147942510LL;
  v10 = *((_QWORD *)v8 + 5);
  if ( v10 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v10 + 40LL))(v10) )
  {
    *((_DWORD *)this + 4) = 1;
    return 0;
  }
  else
  {
    v11 = (void *)*((_QWORD *)this + 1);
    if ( v11 )
    {
      CommonFileMapping::~CommonFileMapping(*((CommonFileMapping **)this + 1));
      operator delete(v11);
      *((_QWORD *)this + 1) = 0;
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18001fae0  mov     [rsp+arg_8], rbx
0x18001fae5  mov     [rsp+arg_10], rsi
0x18001faea  push    rdi
0x18001faeb  sub     rsp, 20h
0x18001faef  mov     ebx, r8d
0x18001faf2  mov     rsi, rdx
0x18001faf5  mov     rdi, rcx
0x18001faf8  cmp     dword ptr [rcx+10h], 0
0x18001fafc  jz      short loc_18001FB08
0x18001fafe  mov     eax, 800704DFh
0x18001fb03  jmp     loc_18001FBB0
0x18001fb08  mov     ecx, 30h ; '0'; Size
0x18001fb0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fb12  mov     [rsp+28h+arg_0], rax
0x18001fb17  test    rax, rax
0x18001fb1a  jz      short loc_18001FB2F
0x18001fb1c  mov     r8d, ebx; int
0x18001fb1f  mov     rdx, rsi; unsigned __int16 *
0x18001fb22  mov     rcx, rax; this
0x18001fb25  call    ??0CommonFileMapping@@QEAA@PEBGH_K@Z; CommonFileMapping::CommonFileMapping(ushort const *,int,unsigned __int64)
0x18001fb2a  mov     rbx, rax
0x18001fb2d  jmp     short loc_18001FB31
0x18001fb2f  xor     ebx, ebx
0x18001fb31  mov     rsi, [rdi+8]
0x18001fb35  cmp     rbx, rsi
0x18001fb38  jz      short loc_18001FB56
0x18001fb3a  test    rsi, rsi
0x18001fb3d  jz      short loc_18001FB50
0x18001fb3f  mov     rcx, rsi; this
0x18001fb42  call    ??1CommonFileMapping@@QEAA@XZ; CommonFileMapping::~CommonFileMapping(void)
0x18001fb47  mov     rcx, rsi
0x18001fb4a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fb50  mov     [rdi+8], rbx
0x18001fb54  jmp     short loc_18001FB59
0x18001fb56  mov     rbx, rsi
0x18001fb59  test    rbx, rbx
0x18001fb5c  jnz     short loc_18001FB65
0x18001fb5e  mov     eax, 8007006Eh
0x18001fb63  jmp     short loc_18001FBB0
0x18001fb65  mov     rcx, [rbx+28h]
0x18001fb69  test    rcx, rcx
0x18001fb6c  jz      short loc_18001FB89
0x18001fb6e  mov     rax, [rcx]
0x18001fb71  mov     rax, [rax+28h]
0x18001fb75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb7a  test    eax, eax
0x18001fb7c  jz      short loc_18001FB89
0x18001fb7e  mov     dword ptr [rdi+10h], 1
0x18001fb85  xor     eax, eax
0x18001fb87  jmp     short loc_18001FBB0
0x18001fb89  mov     rbx, [rdi+8]
0x18001fb8d  test    rbx, rbx
0x18001fb90  jz      short loc_18001FBAB
0x18001fb92  mov     rcx, rbx; this
0x18001fb95  call    ??1CommonFileMapping@@QEAA@XZ; CommonFileMapping::~CommonFileMapping(void)
0x18001fb9a  mov     rcx, rbx
0x18001fb9d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fba3  mov     qword ptr [rdi+8], 0
0x18001fbab  mov     eax, 80004005h
0x18001fbb0  mov     rbx, [rsp+28h+arg_8]
0x18001fbb5  mov     rsi, [rsp+28h+arg_10]
0x18001fbba  add     rsp, 20h
0x18001fbbe  pop     rdi
0x18001fbbf  retn
```
