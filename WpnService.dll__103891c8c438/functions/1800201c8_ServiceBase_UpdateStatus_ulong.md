# ServiceBase::_UpdateStatus(ulong)

- ea: `0x1800201c8`
- end: `0x1800202b3`
- name: `?_UpdateStatus@ServiceBase@@AEAAJK@Z`
- size: `235`
- prototype: `__int64 __fastcall(ServiceBase *this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180013a60`
- `0x18001f588`
- `0x18001fab0`

## callees

- `0x1800201c8`
- `0x1800202bc`
- `0x1800238d0`
- `0x180037010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180020230`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180020230`

## string_xrefs

- `0x1800201e1`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`
- `0x18002023f`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`

## pseudocode

```c
__int64 __fastcall ServiceBase::_UpdateStatus(ServiceBase *this, int a2)
{
  const char *v4; // r9
  __int64 v5; // rax
  __int64 v6; // rax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_QWORD *)this + 9) )
  {
    *((_DWORD *)this + 25) = a2;
    if ( a2 == 1 || a2 == 4 )
    {
      *((_DWORD *)this + 29) = 0;
      if ( a2 == 1 )
      {
        if ( (*(unsigned int (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 72LL))(this) )
        {
          v5 = *(_QWORD *)this;
          *((_DWORD *)this + 27) = 1066;
          *((_DWORD *)this + 28) = (*(__int64 (__fastcall **)(ServiceBase *))(v5 + 72))(this);
        }
      }
      else
      {
        v6 = *(_QWORD *)this;
        *((_DWORD *)this + 26) |= 0x401u;
        *((_DWORD *)this + 26) |= (*(__int64 (**)(void))(v6 + 56))();
      }
    }
    else
    {
      ++*((_DWORD *)this + 29);
      if ( (unsigned int)(a2 - 2) <= 1 )
        *((_DWORD *)this + 30) = (*(__int64 (__fastcall **)(ServiceBase *))(*(_QWORD *)this + 64LL))(this);
    }
    if ( SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 9), (LPSERVICE_STATUS)((char *)this + 96)) )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x160,
               (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
               v4);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
      (const char *)0x80070006LL,
      v7);
    return 2147942406LL;
  }
}

```

## disassembly

```asm
0x1800201c8  mov     [rsp+arg_0], rbx
0x1800201cd  push    rdi; int
0x1800201ce  sub     rsp, 20h
0x1800201d2  cmp     qword ptr [rcx+48h], 0
0x1800201d7  mov     rbx, rcx
0x1800201da  jnz     short loc_180020201
0x1800201dc  mov     rcx, [rsp+28h]; this
0x1800201e1  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800201e8  mov     ebx, 80070006h
0x1800201ed  mov     edx, 136h; void *
0x1800201f2  mov     r9d, ebx; char *
0x1800201f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800201fa  mov     eax, ebx
0x1800201fc  jmp     loc_1800202A8
0x180020201  mov     [rcx+64h], edx
0x180020204  cmp     edx, 1
0x180020207  jz      short loc_180020252
0x180020209  cmp     edx, 4
0x18002020c  jz      short loc_180020252
0x18002020e  inc     dword ptr [rcx+74h]
0x180020211  lea     eax, [rdx-2]
0x180020214  cmp     eax, 1
0x180020217  ja      short loc_180020228
0x180020219  mov     rax, [rcx]
0x18002021c  mov     rax, [rax+40h]
0x180020220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020225  mov     [rbx+78h], eax
0x180020228  mov     rcx, [rbx+48h]; hServiceStatus
0x18002022c  lea     rdx, [rbx+60h]; lpServiceStatus
0x180020230  call    cs:__imp_SetServiceStatus
0x180020236  test    eax, eax
0x180020238  jnz     short loc_1800202A6
0x18002023a  mov     rcx, [rsp+28h]; this
0x18002023f  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180020246  mov     edx, 160h; void *
0x18002024b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020250  jmp     short loc_1800202A8
0x180020252  mov     dword ptr [rcx+74h], 0
0x180020259  cmp     edx, 1
0x18002025c  jnz     short loc_180020289
0x18002025e  mov     rax, [rcx]
0x180020261  mov     rax, [rax+48h]
0x180020265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002026a  test    eax, eax
0x18002026c  jz      short loc_180020228
0x18002026e  mov     rax, [rbx]
0x180020271  mov     rcx, rbx
0x180020274  mov     dword ptr [rbx+6Ch], 42Ah
0x18002027b  mov     rax, [rax+48h]
0x18002027f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020284  mov     [rbx+70h], eax
0x180020287  jmp     short loc_180020228
0x180020289  cmp     edx, 4
0x18002028c  jnz     short loc_180020211
0x18002028e  mov     rax, [rcx]
0x180020291  or      dword ptr [rcx+68h], 401h
0x180020298  mov     rax, [rax+38h]
0x18002029c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202a1  or      [rbx+68h], eax
0x1800202a4  jmp     short loc_180020228
0x1800202a6  xor     eax, eax
0x1800202a8  mov     rbx, [rsp+28h+arg_0]
0x1800202ad  add     rsp, 20h
0x1800202b1  pop     rdi
0x1800202b2  retn
```
