# CSyncServices::CreateMemoryConflictLog(IMemoryConflictLog * *)

- ea: `0x18002c150`
- end: `0x18002c2af`
- name: `?CreateMemoryConflictLog@CSyncServices@@UEAAJPEAPEAUIMemoryConflictLog@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(CSyncServices *__hidden this, struct IMemoryConflictLog **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002c150`
- `0x180094010`

## string_xrefs

- `0x18002c184`: `CSyncServices::CreateMemoryConflictLog`
- `0x18002c286`: `CSyncServices::CreateMemoryConflictLog`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateMemoryConflictLog(CSyncServices *this, struct IMemoryConflictLog **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  _QWORD *v6; // rdi
  __int64 v7; // rax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateMemoryConflictLog");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147217407;
  if ( *((_QWORD *)this + 5) )
  {
    v5 = -2147467261;
    if ( a2 )
    {
      v5 = -2147024882;
      v6 = SeAlloc(0x58u);
      if ( v6 )
      {
        v7 = *((_QWORD *)this + 5);
        *v6 = &CInMemoryConflictLog::`vftable'{for `IMemoryConflictLog'};
        v6[1] = &CInMemoryConflictLog::`vftable'{for `IConflictLogAccess'};
        v6[2] = &CInMemoryConflictLog::`vftable'{for `IConflictLogWriter'};
        *((_DWORD *)v6 + 6) = 1;
        *((_DWORD *)v6 + 16) = 1;
        *((_DWORD *)v6 + 10) = 0;
        v6[6] = 0;
        v6[7] = 0;
        v6[9] = 0;
        v6[10] = 0;
        v6[4] = v7;
        _InterlockedAdd((volatile signed __int32 *)(v7 + 48), 1u);
        _InterlockedAdd(&g_cRefThisDll, 1u);
        v5 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IMemoryConflictLog **))*v6)(
               v6,
               &GUID_3f68732e_1d6e_4abf_af3f_a505b17652ad,
               a2);
        (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
      }
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      53,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateMemoryConflictLog",
      v5);
  return v5;
}

```

## disassembly

```asm
0x18002c150  push    rbx
0x18002c152  push    rbp
0x18002c153  push    rsi
0x18002c154  push    rdi
0x18002c155  push    r15
0x18002c157  sub     rsp, 30h
0x18002c15b  mov     rsi, rdx
0x18002c15e  mov     rbp, rcx
0x18002c161  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c168  lea     r15, WPP_GLOBAL_Control
0x18002c16f  cmp     rcx, r15
0x18002c172  jz      short loc_18002C1A3
0x18002c174  test    byte ptr [rcx+1Ch], 2
0x18002c178  jz      short loc_18002C1A3
0x18002c17a  cmp     byte ptr [rcx+19h], 5
0x18002c17e  jb      short loc_18002C1A3
0x18002c180  mov     rcx, [rcx+10h]
0x18002c184  lea     r9, aCsyncservicesC_13; "CSyncServices::CreateMemoryConflictLog"
0x18002c18b  mov     edx, 34h ; '4'
0x18002c190  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c197  call    WPP_SF_s
0x18002c19c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c1a3  cmp     qword ptr [rbp+28h], 0
0x18002c1a8  mov     ebx, 80041001h
0x18002c1ad  jz      loc_18002C271
0x18002c1b3  mov     ebx, 80004003h
0x18002c1b8  test    rsi, rsi
0x18002c1bb  jz      loc_18002C271
0x18002c1c1  mov     ecx, 58h ; 'X'; unsigned __int64
0x18002c1c6  mov     ebx, 8007000Eh
0x18002c1cb  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002c1d0  mov     rdi, rax
0x18002c1d3  test    rax, rax
0x18002c1d6  jz      loc_18002C26A
0x18002c1dc  mov     rax, [rbp+28h]
0x18002c1e0  lea     rcx, ??_7CInMemoryConflictLog@@6BIMemoryConflictLog@@@; const CInMemoryConflictLog::`vftable'{for `IMemoryConflictLog'}
0x18002c1e7  mov     [rdi], rcx
0x18002c1ea  lea     rcx, ??_7CInMemoryConflictLog@@6BIConflictLogAccess@@@; const CInMemoryConflictLog::`vftable'{for `IConflictLogAccess'}
0x18002c1f1  mov     [rdi+8], rcx
0x18002c1f5  lea     rcx, ??_7CInMemoryConflictLog@@6BIConflictLogWriter@@@; const CInMemoryConflictLog::`vftable'{for `IConflictLogWriter'}
0x18002c1fc  mov     [rdi+10h], rcx
0x18002c200  mov     ecx, 1
0x18002c205  mov     [rdi+18h], ecx
0x18002c208  mov     [rdi+40h], ecx
0x18002c20b  mov     dword ptr [rdi+28h], 0
0x18002c212  mov     qword ptr [rdi+30h], 0
0x18002c21a  mov     qword ptr [rdi+38h], 0
0x18002c222  mov     qword ptr [rdi+48h], 0
0x18002c22a  mov     qword ptr [rdi+50h], 0
0x18002c232  mov     [rdi+20h], rax
0x18002c236  lock add [rax+30h], ecx
0x18002c23a  lock add cs:?g_cRefThisDll@@3JC, ecx; long volatile g_cRefThisDll
0x18002c241  mov     rax, [rdi]
0x18002c244  lea     rdx, _GUID_3f68732e_1d6e_4abf_af3f_a505b17652ad
0x18002c24b  mov     r8, rsi
0x18002c24e  mov     rcx, rdi
0x18002c251  mov     rax, [rax]
0x18002c254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c259  mov     rcx, [rdi]
0x18002c25c  mov     ebx, eax
0x18002c25e  mov     rax, [rcx+10h]
0x18002c262  mov     rcx, rdi
0x18002c265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c26a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c271  cmp     rcx, r15
0x18002c274  jz      short loc_18002C2A2
0x18002c276  test    byte ptr [rcx+1Ch], 2
0x18002c27a  jz      short loc_18002C2A2
0x18002c27c  cmp     byte ptr [rcx+19h], 5
0x18002c280  jb      short loc_18002C2A2
0x18002c282  mov     rcx, [rcx+10h]
0x18002c286  lea     r9, aCsyncservicesC_13; "CSyncServices::CreateMemoryConflictLog"
0x18002c28d  mov     edx, 35h ; '5'
0x18002c292  mov     [rsp+58h+var_38], ebx
0x18002c296  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c29d  call    WPP_SF_sD
0x18002c2a2  mov     eax, ebx
0x18002c2a4  add     rsp, 30h
0x18002c2a8  pop     r15
0x18002c2aa  pop     rdi
0x18002c2ab  pop     rsi
0x18002c2ac  pop     rbp
0x18002c2ad  pop     rbx
0x18002c2ae  retn
```
