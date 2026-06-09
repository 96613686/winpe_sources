# CSyncServices::CreateLoggedConflictsEnumBuilder(IEnumLoggedConflictsBuilder * *)

- ea: `0x18002c050`
- end: `0x18002c13e`
- name: `?CreateLoggedConflictsEnumBuilder@CSyncServices@@UEAAJPEAPEAUIEnumLoggedConflictsBuilder@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(CSyncServices *__hidden this, struct IEnumLoggedConflictsBuilder **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002c050`
- `0x18005c7a8`
- `0x18005ca38`
- `0x180094010`

## string_xrefs

- `0x18002c07f`: `CSyncServices::CreateLoggedConflictsEnumBuilder`
- `0x18002c117`: `CSyncServices::CreateLoggedConflictsEnumBuilder`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateLoggedConflictsEnumBuilder(
        CSyncServices *this,
        struct IEnumLoggedConflictsBuilder **a2)
{
  PVOID *v3; // rcx
  int v4; // ebx
  CSyncEnumLoggedConflictsBuilder *v5; // rax
  CSyncEnumLoggedConflictsBuilder *v6; // rax
  struct IEnumLoggedConflictsBuilder *v7; // rdi

  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateLoggedConflictsEnumBuilder");
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  v4 = -2147467261;
  if ( a2 )
  {
    v4 = -2147024882;
    v5 = (CSyncEnumLoggedConflictsBuilder *)SeAlloc(0x18u);
    if ( v5 )
    {
      v6 = CSyncEnumLoggedConflictsBuilder::CSyncEnumLoggedConflictsBuilder(v5);
      v7 = v6;
      if ( v6 )
      {
        v4 = CSyncEnumLoggedConflictsBuilder::Init(v6);
        if ( v4 >= 0 )
        {
          *a2 = v7;
          (*(void (__fastcall **)(struct IEnumLoggedConflictsBuilder *))(*(_QWORD *)v7 + 8LL))(v7);
        }
        (*(void (__fastcall **)(struct IEnumLoggedConflictsBuilder *))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 && *((_BYTE *)v3 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v3[2],
      55,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateLoggedConflictsEnumBuilder",
      v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002c050  push    rbx
0x18002c052  push    rbp
0x18002c053  push    rsi
0x18002c054  push    rdi
0x18002c055  sub     rsp, 38h
0x18002c059  mov     rsi, rdx
0x18002c05c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c063  lea     rbp, WPP_GLOBAL_Control
0x18002c06a  cmp     rcx, rbp
0x18002c06d  jz      short loc_18002C09E
0x18002c06f  test    byte ptr [rcx+1Ch], 2
0x18002c073  jz      short loc_18002C09E
0x18002c075  cmp     byte ptr [rcx+19h], 5
0x18002c079  jb      short loc_18002C09E
0x18002c07b  mov     rcx, [rcx+10h]
0x18002c07f  lea     r9, aCsyncservicesC_19; "CSyncServices::CreateLoggedConflictsEnu"...
0x18002c086  mov     edx, 36h ; '6'
0x18002c08b  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c092  call    WPP_SF_s
0x18002c097  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c09e  mov     ebx, 80004003h
0x18002c0a3  test    rsi, rsi
0x18002c0a6  jz      short loc_18002C102
0x18002c0a8  mov     ecx, 18h; unsigned __int64
0x18002c0ad  mov     ebx, 8007000Eh
0x18002c0b2  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18002c0b7  test    rax, rax
0x18002c0ba  jz      short loc_18002C0FB
0x18002c0bc  mov     rcx, rax; this
0x18002c0bf  call    ??0CSyncEnumLoggedConflictsBuilder@@QEAA@XZ; CSyncEnumLoggedConflictsBuilder::CSyncEnumLoggedConflictsBuilder(void)
0x18002c0c4  mov     rdi, rax
0x18002c0c7  test    rax, rax
0x18002c0ca  jz      short loc_18002C0FB
0x18002c0cc  mov     rcx, rax; this
0x18002c0cf  call    ?Init@CSyncEnumLoggedConflictsBuilder@@QEAAJXZ; CSyncEnumLoggedConflictsBuilder::Init(void)
0x18002c0d4  mov     ebx, eax
0x18002c0d6  test    eax, eax
0x18002c0d8  js      short loc_18002C0EC
0x18002c0da  mov     [rsi], rdi
0x18002c0dd  mov     rcx, [rdi]
0x18002c0e0  mov     rax, [rcx+8]
0x18002c0e4  mov     rcx, rdi
0x18002c0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0ec  mov     rcx, [rdi]
0x18002c0ef  mov     rax, [rcx+10h]
0x18002c0f3  mov     rcx, rdi
0x18002c0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c102  cmp     rcx, rbp
0x18002c105  jz      short loc_18002C133
0x18002c107  test    byte ptr [rcx+1Ch], 2
0x18002c10b  jz      short loc_18002C133
0x18002c10d  cmp     byte ptr [rcx+19h], 5
0x18002c111  jb      short loc_18002C133
0x18002c113  mov     rcx, [rcx+10h]
0x18002c117  lea     r9, aCsyncservicesC_19; "CSyncServices::CreateLoggedConflictsEnu"...
0x18002c11e  mov     edx, 37h ; '7'
0x18002c123  mov     [rsp+58h+var_38], ebx
0x18002c127  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002c12e  call    WPP_SF_sD
0x18002c133  mov     eax, ebx
0x18002c135  add     rsp, 38h
0x18002c139  pop     rdi
0x18002c13a  pop     rsi
0x18002c13b  pop     rbp
0x18002c13c  pop     rbx
0x18002c13d  retn
```
