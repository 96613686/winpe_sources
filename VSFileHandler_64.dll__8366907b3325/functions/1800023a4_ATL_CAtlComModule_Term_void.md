# ATL::CAtlComModule::Term(void)

- ea: `0x1800023a4`
- end: `0x180002413`
- name: `?Term@CAtlComModule@ATL@@QEAAXXZ`
- size: `111`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800253a0`

## callees

- `0x1800023a4`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x1800023d9`
- `KERNEL32!DecodePointer` at `0x1800023d9`
- `KERNEL32!DeleteCriticalSection` at `0x1800023fa`
- `KERNEL32!DeleteCriticalSection` at `0x1800023fa`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::Term(ATL::CAtlComModule *this)
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
0x1800023a4  mov     [rsp+arg_0], rbx
0x1800023a9  mov     [rsp+arg_8], rsi
0x1800023ae  push    rdi
0x1800023af  sub     rsp, 20h
0x1800023b3  cmp     dword ptr [rcx], 0
0x1800023b6  mov     rbx, rcx
0x1800023b9  jz      short loc_180002403
0x1800023bb  mov     rdi, [rcx+10h]
0x1800023bf  cmp     rdi, [rcx+18h]
0x1800023c3  jnb     short loc_1800023F6
0x1800023c5  mov     rax, [rdi]
0x1800023c8  test    rax, rax
0x1800023cb  jz      short loc_1800023EC
0x1800023cd  mov     rsi, [rax+20h]
0x1800023d1  mov     rcx, [rsi]; Ptr
0x1800023d4  test    rcx, rcx
0x1800023d7  jz      short loc_1800023EC
0x1800023d9  call    cs:__imp_DecodePointer
0x1800023df  mov     rcx, rax
0x1800023e2  mov     rdx, [rax]
0x1800023e5  call    qword ptr [rdx+10h]
0x1800023e8  and     qword ptr [rsi], 0
0x1800023ec  add     rdi, 8
0x1800023f0  cmp     rdi, [rbx+18h]
0x1800023f4  jb      short loc_1800023C5
0x1800023f6  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800023fa  call    cs:__imp_DeleteCriticalSection
0x180002400  and     dword ptr [rbx], 0
0x180002403  mov     rbx, [rsp+28h+arg_0]
0x180002408  mov     rsi, [rsp+28h+arg_8]
0x18000240d  add     rsp, 20h
0x180002411  pop     rdi
0x180002412  retn
```
