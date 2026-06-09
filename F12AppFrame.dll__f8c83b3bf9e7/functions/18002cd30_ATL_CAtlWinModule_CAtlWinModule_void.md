# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18002cd30`
- end: `0x18002cde5`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800343d0`

## callees

- `0x180002624`
- `0x180006e00`
- `0x18002cd30`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002cda0`
- `KERNEL32!DeleteCriticalSection` at `0x18002cda0`
- `USER32!UnregisterClassA` at `0x18002cd71`
- `USER32!UnregisterClassA` at `0x18002cd71`

## pseudocode

```c
void __fastcall ATL::CAtlWinModule::~CAtlWinModule(ATL::CAtlWinModule *this, int a2, unsigned int a3)
{
  HINSTANCE v4; // rsi
  int i; // edi
  void *v6; // rcx
  void *v7; // rcx

  if ( this && *(_DWORD *)this == 72 )
  {
    v4 = hInst;
    for ( i = 0; i < *((_DWORD *)this + 16); ++i )
    {
      if ( i < 0 || i >= *((_DWORD *)this + 16) )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, a2, a3);
        JUMPOUT(0x18002CDE4LL);
      }
      UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*((_QWORD *)this + 7) + 2LL * i), v4);
    }
    v6 = (void *)*((_QWORD *)this + 7);
    if ( v6 )
    {
      free(v6);
      *((_QWORD *)this + 7) = 0;
    }
    *((_QWORD *)this + 8) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 0;
  }
  v7 = (void *)*((_QWORD *)this + 7);
  if ( v7 )
  {
    free(v7);
    *((_QWORD *)this + 7) = 0;
  }
  *((_QWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x18002cd30  mov     [rsp+arg_0], rbx
0x18002cd35  mov     [rsp+arg_8], rsi
0x18002cd3a  push    rdi
0x18002cd3b  sub     rsp, 20h
0x18002cd3f  mov     rbx, rcx
0x18002cd42  test    rcx, rcx
0x18002cd45  jz      short loc_18002CDAC
0x18002cd47  cmp     dword ptr [rcx], 48h ; 'H'
0x18002cd4a  jnz     short loc_18002CDAC
0x18002cd4c  mov     rsi, cs:hInst
0x18002cd53  xor     edi, edi
0x18002cd55  cmp     [rcx+40h], edi
0x18002cd58  jle     short loc_18002CD7E
0x18002cd5a  test    edi, edi
0x18002cd5c  js      short loc_18002CDDA
0x18002cd5e  cmp     edi, [rbx+40h]
0x18002cd61  jge     short loc_18002CDDA
0x18002cd63  mov     rax, [rbx+38h]
0x18002cd67  mov     rdx, rsi; hInstance
0x18002cd6a  movsxd  rcx, edi
0x18002cd6d  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18002cd71  call    cs:__imp_UnregisterClassA
0x18002cd77  inc     edi
0x18002cd79  cmp     edi, [rbx+40h]
0x18002cd7c  jl      short loc_18002CD5A
0x18002cd7e  mov     rcx, [rbx+38h]; Block
0x18002cd82  test    rcx, rcx
0x18002cd85  jz      short loc_18002CD94
0x18002cd87  call    free
0x18002cd8c  mov     qword ptr [rbx+38h], 0
0x18002cd94  lea     rcx, [rbx+8]; lpCriticalSection
0x18002cd98  mov     qword ptr [rbx+40h], 0
0x18002cda0  call    cs:__imp_DeleteCriticalSection
0x18002cda6  mov     dword ptr [rbx], 0
0x18002cdac  mov     rcx, [rbx+38h]; Block
0x18002cdb0  test    rcx, rcx
0x18002cdb3  jz      short loc_18002CDC2
0x18002cdb5  call    free
0x18002cdba  mov     qword ptr [rbx+38h], 0
0x18002cdc2  mov     rsi, [rsp+28h+arg_8]
0x18002cdc7  mov     qword ptr [rbx+40h], 0
0x18002cdcf  mov     rbx, [rsp+28h+arg_0]
0x18002cdd4  add     rsp, 20h
0x18002cdd8  pop     rdi
0x18002cdd9  retn
0x18002cdda  mov     ecx, 0C000008Ch; this
0x18002cddf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
