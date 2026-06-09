# sub_18007FEBC

- ea: `0x18007febc`
- end: `0x180080039`
- name: `sub_18007FEBC`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800c1f74`

## callees

- `0x180001f44`
- `0x18001199c`
- `0x18007e8d4`
- `0x18007febc`
- `0x1800c2124`
- `0x1800cb544`
- `0x1800d8190`
- `0x1800d8340`
- `0x1800d84b0`
- `0x180108120`
- `0x18010818c`
- `0x180162d20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007ffd7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007ffd7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18007ff25`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18007ff25`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18007fefe`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18007fefe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007ff9d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007ff9d`
- `mfperfhelper!mfperfhelper_1` at `0x18007fed4`
- `mfperfhelper!mfperfhelper_1` at `0x18007fed4`

## pseudocode

```c
__int64 __fastcall sub_18007FEBC(__int64 a1, unsigned int a2, __int64 a3)
{
  int v5; // eax
  __int64 v6; // rax
  __int64 v8; // rcx

  if ( a2 != 1 )
  {
    if ( !a2 )
    {
      if ( !a3 )
        DeleteCriticalSection(&CriticalSection);
      v8 = qword_180244EC0;
      if ( qword_180244EC0 )
      {
        if ( *(_QWORD *)qword_180244EC0 )
        {
          sub_180108120(*(_QWORD *)qword_180244EC0);
          v8 = qword_180244EC0;
          if ( *(_QWORD *)qword_180244EC0 )
          {
            _o_free(*(_QWORD *)qword_180244EC0);
            v8 = qword_180244EC0;
            *(_QWORD *)qword_180244EC0 = 0;
          }
        }
        j_j__o_free(v8, 8);
        qword_180244EC0 = 0;
      }
      sub_18001199C(&dword_18023D2B0);
      sub_18001199C(&dword_18023D1B8);
      sub_180162D20();
    }
    return sub_18007E8D4(a1, a2);
  }
  v5 = mfperfhelper_1();
  if ( v5 && v5 != 20 )
    return 0;
  dword_180245B20 = 0;
  InitializeCriticalSection(&CriticalSection);
  if ( (int)sub_1800CB544() < 0 )
    return 0;
  if ( !*(_QWORD *)qword_180244EC0 )
  {
    v6 = _o_malloc(56);
    *(_QWORD *)qword_180244EC0 = v6;
    if ( v6 )
    {
      sub_18010818C(v6);
      goto LABEL_8;
    }
    return 0;
  }
LABEL_8:
  sub_180001F44(&dword_18023D2B0);
  sub_180001F44(&dword_18023D1B8);
  sub_1800D8190();
  sub_1800D8340();
  RequestContext = &qword_18023F6A0;
  sub_1800D84B0();
  return sub_18007E8D4(a1, a2);
}

```

## disassembly

```asm
0x18007febc  mov     [rsp+arg_0], rbx
0x18007fec1  push    rdi
0x18007fec2  sub     rsp, 20h
0x18007fec6  mov     ebx, edx
0x18007fec8  mov     rdi, rcx
0x18007fecb  cmp     edx, 1
0x18007fece  jnz     loc_18007FF89
0x18007fed4  call    cs:mfperfhelper_1
0x18007fedb  nop     dword ptr [rax+rax+00h]
0x18007fee0  test    eax, eax
0x18007fee2  jz      short loc_18007FEED
0x18007fee4  cmp     eax, 14h
0x18007fee7  jnz     loc_18007FF82
0x18007feed  lea     rcx, CriticalSection; lpCriticalSection
0x18007fef4  mov     cs:dword_180245B20, 0
0x18007fefe  call    cs:InitializeCriticalSection
0x18007ff05  nop     dword ptr [rax+rax+00h]
0x18007ff0a  call    sub_1800CB544
0x18007ff0f  test    eax, eax
0x18007ff11  js      short loc_18007FF82
0x18007ff13  mov     rax, cs:qword_180244EC0
0x18007ff1a  cmp     qword ptr [rax], 0
0x18007ff1e  jnz     short loc_18007FF48
0x18007ff20  mov     ecx, 38h ; '8'
0x18007ff25  call    cs:__imp__o_malloc
0x18007ff2c  nop     dword ptr [rax+rax+00h]
0x18007ff31  mov     rcx, cs:qword_180244EC0
0x18007ff38  mov     [rcx], rax
0x18007ff3b  test    rax, rax
0x18007ff3e  jz      short loc_18007FF82
0x18007ff40  mov     rcx, rax
0x18007ff43  call    sub_18010818C
0x18007ff48  lea     rcx, dword_18023D2B0; CallbackContext
0x18007ff4f  call    sub_180001F44
0x18007ff54  lea     rcx, dword_18023D1B8; CallbackContext
0x18007ff5b  call    sub_180001F44
0x18007ff60  call    sub_1800D8190
0x18007ff65  call    sub_1800D8340
0x18007ff6a  lea     rcx, qword_18023F6A0
0x18007ff71  mov     cs:RequestContext, rcx
0x18007ff78  call    sub_1800D84B0
0x18007ff7d  jmp     loc_180080023
0x18007ff82  xor     eax, eax
0x18007ff84  jmp     loc_18008002D
0x18007ff89  test    ebx, ebx
0x18007ff8b  jnz     loc_180080023
0x18007ff91  test    r8, r8
0x18007ff94  jnz     short loc_18007FFA9
0x18007ff96  lea     rcx, CriticalSection; lpCriticalSection
0x18007ff9d  call    cs:__imp_DeleteCriticalSection
0x18007ffa4  nop     dword ptr [rax+rax+00h]
0x18007ffa9  mov     rcx, cs:qword_180244EC0
0x18007ffb0  test    rcx, rcx
0x18007ffb3  jz      short loc_180080006
0x18007ffb5  mov     rax, [rcx]
0x18007ffb8  test    rax, rax
0x18007ffbb  jz      short loc_18007FFF1
0x18007ffbd  mov     rcx, rax
0x18007ffc0  call    sub_180108120
0x18007ffc5  mov     rcx, cs:qword_180244EC0
0x18007ffcc  mov     rax, [rcx]
0x18007ffcf  test    rax, rax
0x18007ffd2  jz      short loc_18007FFF1
0x18007ffd4  mov     rcx, rax
0x18007ffd7  call    cs:__imp__o_free
0x18007ffde  nop     dword ptr [rax+rax+00h]
0x18007ffe3  mov     rcx, cs:qword_180244EC0
0x18007ffea  mov     qword ptr [rcx], 0
0x18007fff1  mov     edx, 8
0x18007fff6  call    j_j__o_free
0x18007fffb  mov     cs:qword_180244EC0, 0
0x180080006  lea     rcx, dword_18023D2B0
0x18008000d  call    sub_18001199C
0x180080012  lea     rcx, dword_18023D1B8
0x180080019  call    sub_18001199C
0x18008001e  call    sub_180162D20
0x180080023  mov     edx, ebx
0x180080025  mov     rcx, rdi
0x180080028  call    sub_18007E8D4
0x18008002d  mov     rbx, [rsp+28h+arg_0]
0x180080032  add     rsp, 20h
0x180080036  pop     rdi
0x180080037  retn
```
