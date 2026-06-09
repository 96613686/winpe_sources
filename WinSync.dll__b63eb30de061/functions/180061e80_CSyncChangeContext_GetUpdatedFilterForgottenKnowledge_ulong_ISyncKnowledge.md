# CSyncChangeContext::GetUpdatedFilterForgottenKnowledge(ulong,ISyncKnowledge * *)

- ea: `0x180061e80`
- end: `0x180061f93`
- name: `?GetUpdatedFilterForgottenKnowledge@CSyncChangeContext@@UEAAJKPEAPEAUISyncKnowledge@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(CSyncChangeContext *__hidden this, unsigned int, struct ISyncKnowledge **)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180061e80`
- `0x1800630ac`
- `0x180094010`

## string_xrefs

- `0x180061eb6`: `CSyncChangeContext::GetUpdatedFilterForgottenKnowledge`
- `0x180061f6a`: `CSyncChangeContext::GetUpdatedFilterForgottenKnowledge`

## pseudocode

```c
__int64 __fastcall CSyncChangeContext::GetUpdatedFilterForgottenKnowledge(
        CSyncChangeContext *this,
        unsigned int a2,
        struct ISyncKnowledge **a3)
{
  __int64 v4; // rbp
  PVOID *v6; // rcx
  int updated; // ebx
  struct ISyncKnowledge *v8; // rdx
  __int64 v9; // rcx

  v4 = a2;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids,
      "CSyncChangeContext::GetUpdatedFilterForgottenKnowledge");
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( *((_DWORD *)this + 32) )
    {
      if ( (unsigned int)v4 < *((_DWORD *)this + 35) )
      {
        updated = 0;
        if ( !*((_DWORD *)this + 12)
          || (updated = CSyncChangeContext::UpdateLearnedKnowledges((CSyncChangeContext *)((char *)this - 24)),
              updated >= 0) )
        {
          v8 = *(struct ISyncKnowledge **)(*((_QWORD *)this + 18) + 8 * v4);
          if ( v8 )
          {
            *a3 = v8;
            v9 = *(_QWORD *)(*((_QWORD *)this + 18) + 8 * v4);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
          }
          else
          {
            updated = 1;
            *a3 = 0;
          }
        }
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      else
      {
        updated = -2147024809;
      }
    }
    else
    {
      updated = -2147217379;
    }
  }
  else
  {
    updated = -2147467261;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v6[2],
      55,
      (unsigned int)WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids,
      (unsigned int)"CSyncChangeContext::GetUpdatedFilterForgottenKnowledge",
      updated);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180061e80  push    rbx
0x180061e82  push    rbp
0x180061e83  push    rsi
0x180061e84  push    rdi
0x180061e85  push    r15
0x180061e87  sub     rsp, 30h
0x180061e8b  mov     rsi, r8
0x180061e8e  mov     ebp, edx
0x180061e90  mov     rdi, rcx
0x180061e93  mov     rcx, cs:WPP_GLOBAL_Control
0x180061e9a  lea     r15, WPP_GLOBAL_Control
0x180061ea1  cmp     rcx, r15
0x180061ea4  jz      short loc_180061ED5
0x180061ea6  test    byte ptr [rcx+1Ch], 8
0x180061eaa  jz      short loc_180061ED5
0x180061eac  cmp     byte ptr [rcx+19h], 5
0x180061eb0  jb      short loc_180061ED5
0x180061eb2  mov     rcx, [rcx+10h]
0x180061eb6  lea     r9, aCsyncchangecon_14; "CSyncChangeContext::GetUpdatedFilterFor"...
0x180061ebd  mov     edx, 36h ; '6'
0x180061ec2  lea     r8, WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids
0x180061ec9  call    WPP_SF_s
0x180061ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180061ed5  test    rsi, rsi
0x180061ed8  jnz     short loc_180061EE1
0x180061eda  mov     ebx, 80004003h
0x180061edf  jmp     short loc_180061F55
0x180061ee1  cmp     dword ptr [rdi+80h], 0
0x180061ee8  jnz     short loc_180061EF1
0x180061eea  mov     ebx, 8004101Dh
0x180061eef  jmp     short loc_180061F55
0x180061ef1  cmp     ebp, [rdi+8Ch]
0x180061ef7  jb      short loc_180061F00
0x180061ef9  mov     ebx, 80070057h
0x180061efe  jmp     short loc_180061F55
0x180061f00  xor     ebx, ebx
0x180061f02  lea     rcx, [rdi-18h]; this
0x180061f06  cmp     [rcx+48h], ebx
0x180061f09  jz      short loc_180061F16
0x180061f0b  call    ?UpdateLearnedKnowledges@CSyncChangeContext@@AEAAJXZ; CSyncChangeContext::UpdateLearnedKnowledges(void)
0x180061f10  mov     ebx, eax
0x180061f12  test    eax, eax
0x180061f14  js      short loc_180061F4E
0x180061f16  mov     rax, [rdi+90h]
0x180061f1d  mov     rdx, [rax+rbp*8]
0x180061f21  test    rdx, rdx
0x180061f24  jz      short loc_180061F42
0x180061f26  mov     [rsi], rdx
0x180061f29  mov     rax, [rdi+90h]
0x180061f30  mov     rcx, [rax+rbp*8]
0x180061f34  mov     rax, [rcx]
0x180061f37  mov     rax, [rax+8]
0x180061f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f40  jmp     short loc_180061F4E
0x180061f42  mov     ebx, 1
0x180061f47  mov     qword ptr [rsi], 0
0x180061f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180061f55  cmp     rcx, r15
0x180061f58  jz      short loc_180061F86
0x180061f5a  test    byte ptr [rcx+1Ch], 8
0x180061f5e  jz      short loc_180061F86
0x180061f60  cmp     byte ptr [rcx+19h], 5
0x180061f64  jb      short loc_180061F86
0x180061f66  mov     rcx, [rcx+10h]
0x180061f6a  lea     r9, aCsyncchangecon_14; "CSyncChangeContext::GetUpdatedFilterFor"...
0x180061f71  mov     edx, 37h ; '7'
0x180061f76  mov     [rsp+58h+var_38], ebx
0x180061f7a  lea     r8, WPP_7c6da4bb1ec73f2e8e9927c67ad3fe7a_Traceguids
0x180061f81  call    WPP_SF_sD
0x180061f86  mov     eax, ebx
0x180061f88  add     rsp, 30h
0x180061f8c  pop     r15
0x180061f8e  pop     rdi
0x180061f8f  pop     rsi
0x180061f90  pop     rbp
0x180061f91  pop     rbx
0x180061f92  retn
```
