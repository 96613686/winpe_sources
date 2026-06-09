# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800013e0`
- end: `0x180001485`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001540`
- `0x180029c40`

## callees

- `0x180001380`
- `0x1800013e0`
- `0x1800268f4`
- `0x180027910`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000145b`
- `KERNEL32!DeleteCriticalSection` at `0x18000145b`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, unsigned int a2)
{
  char *v2; // rsi
  _QWORD *v4; // r14
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v2 = (char *)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      if ( this == (ATL::CAtlModule *)-8LL )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x180001484LL);
      }
      v4 = (_QWORD *)*((_QWORD *)this + 2);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          operator delete(v4);
          v4 = v5;
        }
        while ( v5 );
      }
      *((_QWORD *)v2 + 1) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x1800013e0  mov     [rsp+arg_0], rbx
0x1800013e5  mov     [rsp+arg_8], rsi
0x1800013ea  mov     [rsp+arg_10], rdi
0x1800013ef  push    r14
0x1800013f1  sub     rsp, 20h
0x1800013f5  lea     rsi, [rcx+8]
0x1800013f9  mov     rdi, rcx
0x1800013fc  cmp     dword ptr [rsi], 0
0x1800013ff  jz      short loc_180001464
0x180001401  cmp     qword ptr [rcx+10h], 0
0x180001406  jz      short loc_180001441
0x180001408  test    rsi, rsi
0x18000140b  jz      short loc_18000147A
0x18000140d  mov     r14, [rsi+8]
0x180001411  test    r14, r14
0x180001414  jz      short loc_180001437
0x180001416  mov     rcx, [r14+8]
0x18000141a  mov     rax, [r14]
0x18000141d  call    cs:__guard_dispatch_icall_fptr
0x180001423  mov     rbx, [r14+10h]
0x180001427  mov     rcx, r14; Block
0x18000142a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000142f  mov     r14, rbx
0x180001432  test    rbx, rbx
0x180001435  jnz     short loc_180001416
0x180001437  and     qword ptr [rsi+8], 0
0x18000143c  and     qword ptr [rdi+10h], 0
0x180001441  mov     rcx, [rdi+40h]
0x180001445  test    rcx, rcx
0x180001448  jz      short loc_180001457
0x18000144a  mov     rax, [rcx]
0x18000144d  mov     rax, [rax+10h]
0x180001451  call    cs:__guard_dispatch_icall_fptr
0x180001457  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000145b  call    cs:__imp_DeleteCriticalSection
0x180001461  and     dword ptr [rsi], 0
0x180001464  mov     rbx, [rsp+28h+arg_0]
0x180001469  mov     rsi, [rsp+28h+arg_8]
0x18000146e  mov     rdi, [rsp+28h+arg_10]
0x180001473  add     rsp, 20h
0x180001477  pop     r14
0x180001479  retn
0x18000147a  mov     ecx, 0C0000005h; unsigned int
0x18000147f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
