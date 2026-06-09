# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000b408`
- end: `0x18000b4bf`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011590`

## callees

- `0x1800090c4`
- `0x18000b408`

## import_xrefs

- `msvcrt!free` at `0x18000b45f`
- `msvcrt!free` at `0x18000b48e`
- `msvcrt!free` at `0x18000b45f`
- `msvcrt!free` at `0x18000b48e`
- `KERNEL32!DeleteCriticalSection` at `0x18000b479`
- `KERNEL32!DeleteCriticalSection` at `0x18000b479`
- `USER32!UnregisterClassA` at `0x18000b449`
- `USER32!UnregisterClassA` at `0x18000b449`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this, unsigned int a2)
{
  HINSTANCE v3; // rsi
  int i; // edi
  void *v5; // rcx
  void *v6; // rcx

  if ( this && *(_DWORD *)this == 72 )
  {
    v3 = hInstance;
    for ( i = 0; i < *((_DWORD *)this + 16); ++i )
    {
      if ( i < 0 || i >= *((_DWORD *)this + 16) )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x18000B4BELL);
      }
      UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*((_QWORD *)this + 7) + 2LL * i), v3);
    }
    v5 = (void *)*((_QWORD *)this + 7);
    if ( v5 )
    {
      free(v5);
      *((_QWORD *)this + 7) = 0;
    }
    *((_QWORD *)this + 8) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  v6 = (void *)*((_QWORD *)this + 7);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 7) = 0;
  }
  *((_QWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x18000b408  mov     [rsp+arg_0], rbx
0x18000b40d  mov     [rsp+arg_8], rsi
0x18000b412  push    rdi
0x18000b413  sub     rsp, 20h
0x18000b417  mov     rbx, rcx
0x18000b41a  test    rcx, rcx
0x18000b41d  jz      short loc_18000B485
0x18000b41f  cmp     dword ptr [rcx], 48h ; 'H'
0x18000b422  jnz     short loc_18000B485
0x18000b424  mov     rsi, cs:hInstance
0x18000b42b  xor     edi, edi
0x18000b42d  cmp     [rcx+40h], edi
0x18000b430  jle     short loc_18000B456
0x18000b432  test    edi, edi
0x18000b434  js      short loc_18000B4B4
0x18000b436  cmp     edi, [rbx+40h]
0x18000b439  jge     short loc_18000B4B4
0x18000b43b  mov     rax, [rbx+38h]
0x18000b43f  mov     rdx, rsi; hInstance
0x18000b442  movsxd  rcx, edi
0x18000b445  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000b449  call    cs:__imp_UnregisterClassA
0x18000b44f  inc     edi
0x18000b451  cmp     edi, [rbx+40h]
0x18000b454  jl      short loc_18000B432
0x18000b456  mov     rcx, [rbx+38h]; Block
0x18000b45a  test    rcx, rcx
0x18000b45d  jz      short loc_18000B46D
0x18000b45f  call    cs:__imp_free
0x18000b465  mov     qword ptr [rbx+38h], 0
0x18000b46d  lea     rcx, [rbx+8]; lpCriticalSection
0x18000b471  mov     qword ptr [rbx+40h], 0
0x18000b479  call    cs:__imp_DeleteCriticalSection
0x18000b47f  mov     dword ptr [rbx], 0
0x18000b485  mov     rcx, [rbx+38h]; Block
0x18000b489  test    rcx, rcx
0x18000b48c  jz      short loc_18000B49C
0x18000b48e  call    cs:__imp_free
0x18000b494  mov     qword ptr [rbx+38h], 0
0x18000b49c  mov     rsi, [rsp+28h+arg_8]
0x18000b4a1  mov     qword ptr [rbx+40h], 0
0x18000b4a9  mov     rbx, [rsp+28h+arg_0]
0x18000b4ae  add     rsp, 20h
0x18000b4b2  pop     rdi
0x18000b4b3  retn
0x18000b4b4  mov     ecx, 0C000008Ch; unsigned int
0x18000b4b9  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
