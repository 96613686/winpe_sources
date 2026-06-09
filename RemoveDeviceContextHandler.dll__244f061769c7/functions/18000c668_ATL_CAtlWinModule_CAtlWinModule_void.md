# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x18000c668`
- end: `0x18000c71f`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d010`

## callees

- `0x18000b5c4`
- `0x18000c668`

## import_xrefs

- `msvcrt!free` at `0x18000c6bf`
- `msvcrt!free` at `0x18000c6ee`
- `msvcrt!free` at `0x18000c6bf`
- `msvcrt!free` at `0x18000c6ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c6d9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c6d9`
- `USER32!UnregisterClassA` at `0x18000c6a9`
- `USER32!UnregisterClassA` at `0x18000c6a9`

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
        JUMPOUT(0x18000C71ELL);
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
0x18000c668  mov     [rsp+arg_0], rbx
0x18000c66d  mov     [rsp+arg_8], rsi
0x18000c672  push    rdi
0x18000c673  sub     rsp, 20h
0x18000c677  mov     rbx, rcx
0x18000c67a  test    rcx, rcx
0x18000c67d  jz      short loc_18000C6E5
0x18000c67f  cmp     dword ptr [rcx], 48h ; 'H'
0x18000c682  jnz     short loc_18000C6E5
0x18000c684  mov     rsi, cs:hInstance
0x18000c68b  xor     edi, edi
0x18000c68d  cmp     [rcx+40h], edi
0x18000c690  jle     short loc_18000C6B6
0x18000c692  test    edi, edi
0x18000c694  js      short loc_18000C714
0x18000c696  cmp     edi, [rbx+40h]
0x18000c699  jge     short loc_18000C714
0x18000c69b  mov     rax, [rbx+38h]
0x18000c69f  mov     rdx, rsi; hInstance
0x18000c6a2  movsxd  rcx, edi
0x18000c6a5  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000c6a9  call    cs:__imp_UnregisterClassA
0x18000c6af  inc     edi
0x18000c6b1  cmp     edi, [rbx+40h]
0x18000c6b4  jl      short loc_18000C692
0x18000c6b6  mov     rcx, [rbx+38h]; Block
0x18000c6ba  test    rcx, rcx
0x18000c6bd  jz      short loc_18000C6CD
0x18000c6bf  call    cs:__imp_free
0x18000c6c5  mov     qword ptr [rbx+38h], 0
0x18000c6cd  lea     rcx, [rbx+8]; lpCriticalSection
0x18000c6d1  mov     qword ptr [rbx+40h], 0
0x18000c6d9  call    cs:__imp_DeleteCriticalSection
0x18000c6df  mov     dword ptr [rbx], 0
0x18000c6e5  mov     rcx, [rbx+38h]; Block
0x18000c6e9  test    rcx, rcx
0x18000c6ec  jz      short loc_18000C6FC
0x18000c6ee  call    cs:__imp_free
0x18000c6f4  mov     qword ptr [rbx+38h], 0
0x18000c6fc  mov     rsi, [rsp+28h+arg_8]
0x18000c701  mov     qword ptr [rbx+40h], 0
0x18000c709  mov     rbx, [rsp+28h+arg_0]
0x18000c70e  add     rsp, 20h
0x18000c712  pop     rdi
0x18000c713  retn
0x18000c714  mov     ecx, 0C000008Ch; unsigned int
0x18000c719  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
