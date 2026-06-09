# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180003088`
- end: `0x180003101`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `121`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f300`

## callees

- `0x180003088`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800030e8`
- `KERNEL32!DeleteCriticalSection` at `0x1800030e8`
- `KERNEL32!DecodePointer` at `0x1800030bd`
- `KERNEL32!DecodePointer` at `0x1800030bd`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::~CAtlComModule(ATL::CAtlComModule *this)
{
  unsigned __int64 i; // rdi
  PVOID *v3; // rsi
  PVOID v4; // rax

  if ( *(_DWORD *)this )
  {
    for ( i = *((_QWORD *)this + 2); i < *((_QWORD *)this + 3); i += 8LL )
    {
      if ( *(_QWORD *)i )
      {
        v3 = *(PVOID **)(*(_QWORD *)i + 32LL);
        if ( *v3 )
        {
          v4 = DecodePointer(*v3);
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v4 + 16LL))(v4);
          *v3 = 0;
        }
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180003088  mov     [rsp+arg_0], rbx
0x18000308d  mov     [rsp+arg_8], rsi
0x180003092  push    rdi
0x180003093  sub     rsp, 20h
0x180003097  mov     rbx, rcx
0x18000309a  cmp     dword ptr [rcx], 0
0x18000309d  jz      short loc_1800030F1
0x18000309f  mov     rdi, [rcx+10h]
0x1800030a3  cmp     rdi, [rcx+18h]
0x1800030a7  jnb     short loc_1800030E4
0x1800030a9  mov     rax, [rdi]
0x1800030ac  test    rax, rax
0x1800030af  jz      short loc_1800030DA
0x1800030b1  mov     rsi, [rax+20h]
0x1800030b5  mov     rcx, [rsi]; Ptr
0x1800030b8  test    rcx, rcx
0x1800030bb  jz      short loc_1800030DA
0x1800030bd  call    cs:__imp_DecodePointer
0x1800030c3  mov     rdx, rax
0x1800030c6  mov     rcx, [rax]
0x1800030c9  mov     rax, [rcx+10h]
0x1800030cd  mov     rcx, rdx
0x1800030d0  call    cs:__guard_dispatch_icall_fptr
0x1800030d6  and     qword ptr [rsi], 0
0x1800030da  add     rdi, 8
0x1800030de  cmp     rdi, [rbx+18h]
0x1800030e2  jb      short loc_1800030A9
0x1800030e4  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800030e8  call    cs:__imp_DeleteCriticalSection
0x1800030ee  and     dword ptr [rbx], 0
0x1800030f1  mov     rbx, [rsp+28h+arg_0]
0x1800030f6  mov     rsi, [rsp+28h+arg_8]
0x1800030fb  add     rsp, 20h
0x1800030ff  pop     rdi
0x180003100  retn
```
