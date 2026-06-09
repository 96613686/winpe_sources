# CASFLanguageListObject::RemoveAll(void)

- ea: `0x18000fd20`
- end: `0x18000fda4`
- name: `?RemoveAll@CASFLanguageListObject@@UEAAJXZ`
- size: `132`
- prototype: `__int64 __fastcall(CASFLanguageListObject *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800049b8`
- `0x18000f12c`
- `0x18000fd20`

## pseudocode

```c
__int64 __fastcall CASFLanguageListObject::RemoveAll(struct IWMSCriticalSection **this)
{
  unsigned int v2; // ebx
  unsigned int v3; // esi
  unsigned int i; // edi
  void *v5; // rax
  char v7; // [rsp+30h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v7, this[4]);
  if ( this[5] )
  {
    v3 = *((_DWORD *)this + 76);
    for ( i = 0; i < v3; ++i )
    {
      v5 = (void *)CTDynArray<unsigned short *,20>::operator[](this + 11, i);
      operator delete(v5);
    }
    CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::FreeList((__int64)(this + 11));
    *((_DWORD *)this + 76) = 0;
    v2 = 0;
  }
  else
  {
    v2 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v7);
  return v2;
}

```

## disassembly

```asm
0x18000fd20  mov     [rsp+arg_8], rbx
0x18000fd25  mov     [rsp+arg_10], rsi
0x18000fd2a  push    rdi
0x18000fd2b  sub     rsp, 20h
0x18000fd2f  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18000fd33  mov     rbx, rcx
0x18000fd36  lea     rcx, [rsp+28h+arg_0]; this
0x18000fd3b  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000fd40  cmp     qword ptr [rbx+28h], 0
0x18000fd45  jnz     short loc_18000FD4E
0x18000fd47  mov     ebx, 0C00D07F6h
0x18000fd4c  jmp     short loc_18000FD88
0x18000fd4e  mov     esi, [rbx+130h]
0x18000fd54  xor     edi, edi
0x18000fd56  test    esi, esi
0x18000fd58  jz      short loc_18000FD73
0x18000fd5a  mov     edx, edi
0x18000fd5c  lea     rcx, [rbx+58h]
0x18000fd60  call    ??A?$CTDynArray@PEAG$0BE@@@QEBAPEAGK@Z; CTDynArray<ushort *,20>::operator[](ulong)
0x18000fd65  mov     rcx, rax; Block
0x18000fd68  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fd6d  inc     edi
0x18000fd6f  cmp     edi, esi
0x18000fd71  jb      short loc_18000FD5A
0x18000fd73  lea     rcx, [rbx+58h]
0x18000fd77  call    ?FreeList@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::FreeList(int)
0x18000fd7c  mov     dword ptr [rbx+130h], 0
0x18000fd86  xor     ebx, ebx
0x18000fd88  lea     rcx, [rsp+28h+arg_0]; this
0x18000fd8d  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18000fd92  mov     rsi, [rsp+28h+arg_10]
0x18000fd97  mov     eax, ebx
0x18000fd99  mov     rbx, [rsp+28h+arg_8]
0x18000fd9e  add     rsp, 20h
0x18000fda2  pop     rdi
0x18000fda3  retn
```
