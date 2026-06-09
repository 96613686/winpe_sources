# ATL::CAtlWinModule::~CAtlWinModule(void)

- ea: `0x14000bc00`
- end: `0x14000bcb7`
- name: `??1CAtlWinModule@ATL@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400162b0`

## callees

- `0x14000a74c`
- `0x14000bc00`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000bc71`
- `KERNEL32!DeleteCriticalSection` at `0x14000bc71`
- `USER32!UnregisterClassA` at `0x14000bc41`
- `USER32!UnregisterClassA` at `0x14000bc41`
- `msvcrt!free` at `0x14000bc57`
- `msvcrt!free` at `0x14000bc86`
- `msvcrt!free` at `0x14000bc57`
- `msvcrt!free` at `0x14000bc86`

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
        JUMPOUT(0x14000BCB6LL);
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
0x14000bc00  mov     [rsp+arg_0], rbx
0x14000bc05  mov     [rsp+arg_8], rsi
0x14000bc0a  push    rdi
0x14000bc0b  sub     rsp, 20h
0x14000bc0f  mov     rbx, rcx
0x14000bc12  test    rcx, rcx
0x14000bc15  jz      short loc_14000BC7D
0x14000bc17  cmp     dword ptr [rcx], 48h ; 'H'
0x14000bc1a  jnz     short loc_14000BC7D
0x14000bc1c  mov     rsi, cs:hInstance
0x14000bc23  xor     edi, edi
0x14000bc25  cmp     [rcx+40h], edi
0x14000bc28  jle     short loc_14000BC4E
0x14000bc2a  test    edi, edi
0x14000bc2c  js      short loc_14000BCAC
0x14000bc2e  cmp     edi, [rbx+40h]
0x14000bc31  jge     short loc_14000BCAC
0x14000bc33  mov     rax, [rbx+38h]
0x14000bc37  mov     rdx, rsi; hInstance
0x14000bc3a  movsxd  rcx, edi
0x14000bc3d  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x14000bc41  call    cs:__imp_UnregisterClassA
0x14000bc47  inc     edi
0x14000bc49  cmp     edi, [rbx+40h]
0x14000bc4c  jl      short loc_14000BC2A
0x14000bc4e  mov     rcx, [rbx+38h]; Block
0x14000bc52  test    rcx, rcx
0x14000bc55  jz      short loc_14000BC65
0x14000bc57  call    cs:__imp_free
0x14000bc5d  mov     qword ptr [rbx+38h], 0
0x14000bc65  lea     rcx, [rbx+8]; lpCriticalSection
0x14000bc69  mov     qword ptr [rbx+40h], 0
0x14000bc71  call    cs:__imp_DeleteCriticalSection
0x14000bc77  mov     dword ptr [rbx], 0
0x14000bc7d  mov     rcx, [rbx+38h]; Block
0x14000bc81  test    rcx, rcx
0x14000bc84  jz      short loc_14000BC94
0x14000bc86  call    cs:__imp_free
0x14000bc8c  mov     qword ptr [rbx+38h], 0
0x14000bc94  mov     rsi, [rsp+28h+arg_8]
0x14000bc99  mov     qword ptr [rbx+40h], 0
0x14000bca1  mov     rbx, [rsp+28h+arg_0]
0x14000bca6  add     rsp, 20h
0x14000bcaa  pop     rdi
0x14000bcab  retn
0x14000bcac  mov     ecx, 0C000008Ch; unsigned int
0x14000bcb1  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
