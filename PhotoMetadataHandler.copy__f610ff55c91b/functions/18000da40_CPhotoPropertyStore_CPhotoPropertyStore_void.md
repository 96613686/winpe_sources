# CPhotoPropertyStore::~CPhotoPropertyStore(void)

- ea: `0x18000da40`
- end: `0x18000dad3`
- name: `??1CPhotoPropertyStore@@QEAA@XZ`
- size: `147`
- prototype: `void __fastcall(CPhotoPropertyStore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d9dc`

## callees

- `0x18000da40`
- `0x18000dadc`
- `0x1800110b8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da4d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dab7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da4d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dab7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPhotoPropertyStore::~CPhotoPropertyStore(CPhotoPropertyStore *this)
{
  const struct _GUID *v2; // rcx
  unsigned __int64 v3; // r8
  __int64 v4; // rcx
  __int64 v5; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v3 = *((_QWORD *)WPP_GLOBAL_Control + 7);
  if ( v3 )
    ShellPrivateTraceEvent(v2, 0x14u, v3, 2u);
  CMetadataContainer::~CMetadataContainer((CPhotoPropertyStore *)((char *)this + 200));
  v4 = *((_QWORD *)this + 18);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 17);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  _InterlockedDecrement((_DWORD *)&qword_180098F58 + 1);
  if ( *((_BYTE *)this + 80) )
  {
    *((_BYTE *)this + 80) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  }
}

```

## disassembly

```asm
0x18000da40  push    rbx
0x18000da42  sub     rsp, 20h
0x18000da46  mov     rbx, rcx
0x18000da49  add     rcx, 60h ; '`'; lpCriticalSection
0x18000da4d  call    cs:__imp_DeleteCriticalSection
0x18000da53  mov     rax, cs:WPP_GLOBAL_Control
0x18000da5a  mov     r8, [rax+38h]; unsigned __int64
0x18000da5e  test    r8, r8
0x18000da61  jnz     short loc_18000DAC4
0x18000da63  lea     rcx, [rbx+0C8h]; this
0x18000da6a  call    ??1CMetadataContainer@@QEAA@XZ; CMetadataContainer::~CMetadataContainer(void)
0x18000da6f  nop
0x18000da70  mov     rcx, [rbx+90h]
0x18000da77  test    rcx, rcx
0x18000da7a  jz      short loc_18000DA89
0x18000da7c  mov     rax, [rcx]
0x18000da7f  mov     rax, [rax+10h]
0x18000da83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da88  nop
0x18000da89  mov     rcx, [rbx+88h]
0x18000da90  test    rcx, rcx
0x18000da93  jz      short loc_18000DAA2
0x18000da95  mov     rax, [rcx]
0x18000da98  mov     rax, [rax+10h]
0x18000da9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daa1  nop
0x18000daa2  lock dec dword ptr cs:qword_180098F58+4
0x18000daa9  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000daad  cmp     byte ptr [rcx+28h], 0
0x18000dab1  jz      short loc_18000DABE
0x18000dab3  mov     byte ptr [rcx+28h], 0
0x18000dab7  call    cs:__imp_DeleteCriticalSection
0x18000dabd  nop
0x18000dabe  add     rsp, 20h
0x18000dac2  pop     rbx
0x18000dac3  retn
0x18000dac4  mov     r9b, 2; unsigned __int8
0x18000dac7  mov     edx, 14h; unsigned int
0x18000dacc  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000dad1  jmp     short loc_18000DA63
```
