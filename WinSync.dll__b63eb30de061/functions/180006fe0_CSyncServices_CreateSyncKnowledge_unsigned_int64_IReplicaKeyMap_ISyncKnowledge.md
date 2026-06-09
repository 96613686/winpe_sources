# CSyncServices::CreateSyncKnowledge(unsigned __int64,IReplicaKeyMap *,ISyncKnowledge * *)

- ea: `0x180006fe0`
- end: `0x18000710c`
- name: `?CreateSyncKnowledge@CSyncServices@@UEAAJ_KPEAUIReplicaKeyMap@@PEAPEAUISyncKnowledge@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(CSyncServices *this, unsigned __int64, struct IReplicaKeyMap *, struct ISyncKnowledge **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002c5f0`

## callees

- `0x180006fe0`
- `0x180008df4`
- `0x18001a038`
- `0x18001ae20`

## string_xrefs

- `0x1800070b9`: `CSyncServices::CreateSyncKnowledge`
- `0x1800070eb`: `CSyncServices::CreateSyncKnowledge`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateSyncKnowledge(
        CSyncServices *this,
        unsigned __int64 a2,
        struct IReplicaKeyMap *a3,
        struct ISyncKnowledge **a4)
{
  PVOID *v8; // rcx
  ID_PARAMETER_PAIR *v9; // rdx
  unsigned int v10; // ebx
  unsigned int v12; // eax
  struct _ID_PARAMETERS v13; // [rsp+30h] [rbp-48h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateSyncKnowledge");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = (ID_PARAMETER_PAIR *)*((_QWORD *)this + 6);
  if ( v9 )
  {
    v13.replicaId = *v9;
    *(&v13.replicaId.cbIdSize + 1) = 0;
    v13.itemId = v9[2];
    *(&v13.itemId.cbIdSize + 1) = 0;
    v13.changeUnitId = v9[4];
    *(&v13.changeUnitId.cbIdSize + 1) = 0;
    v13.dwSize = 28;
    v12 = KnowledgeServices::CreateSyncKnowledge(&v13, a2, a3, a4);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v10 = v12;
  }
  else
  {
    v10 = -2147217407;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      31,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateSyncKnowledge",
      v10);
  return v10;
}

```

## disassembly

```asm
0x180006fe0  push    rbx
0x180006fe2  push    rbp
0x180006fe3  push    rsi
0x180006fe4  push    rdi
0x180006fe5  push    r14
0x180006fe7  sub     rsp, 50h
0x180006feb  mov     rdi, r9
0x180006fee  mov     rsi, r8
0x180006ff1  mov     rbp, rdx
0x180006ff4  mov     rbx, rcx
0x180006ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ffe  lea     r14, WPP_GLOBAL_Control
0x180007005  cmp     rcx, r14
0x180007008  jz      short loc_180007014
0x18000700a  test    byte ptr [rcx+1Ch], 2
0x18000700e  jnz     loc_1800070AB
0x180007014  mov     rdx, [rbx+30h]
0x180007018  test    rdx, rdx
0x18000701b  jnz     short loc_18000703E
0x18000701d  mov     ebx, 80041001h
0x180007022  cmp     rcx, r14
0x180007025  jz      short loc_180007031
0x180007027  test    byte ptr [rcx+1Ch], 2
0x18000702b  jnz     loc_1800070DD
0x180007031  mov     eax, ebx
0x180007033  add     rsp, 50h
0x180007037  pop     r14
0x180007039  pop     rdi
0x18000703a  pop     rsi
0x18000703b  pop     rbp
0x18000703c  pop     rbx
0x18000703d  retn
0x18000703e  mov     eax, [rdx]
0x180007040  lea     rcx, [rsp+78h+var_48]; struct _ID_PARAMETERS *
0x180007045  mov     [rsp+78h+var_48.replicaId.fIsVariable], eax
0x180007049  mov     r9, rdi; struct ISyncKnowledge **
0x18000704c  movzx   eax, word ptr [rdx+4]
0x180007050  mov     r8, rsi; struct IReplicaKeyMap *
0x180007053  mov     [rsp+78h+var_48.replicaId.cbIdSize], ax
0x180007058  xor     eax, eax
0x18000705a  mov     word ptr [rsp+78h+var_48.replicaId+6], ax
0x18000705f  mov     eax, [rdx+10h]
0x180007062  mov     [rsp+78h+var_48.itemId.fIsVariable], eax
0x180007066  movzx   eax, word ptr [rdx+14h]
0x18000706a  mov     [rsp+78h+var_48.itemId.cbIdSize], ax
0x18000706f  xor     eax, eax
0x180007071  mov     word ptr [rsp+78h+var_48.itemId+6], ax
0x180007076  mov     eax, [rdx+20h]
0x180007079  mov     [rsp+78h+var_48.changeUnitId.fIsVariable], eax
0x18000707d  movzx   eax, word ptr [rdx+24h]
0x180007081  mov     rdx, rbp; unsigned __int64
0x180007084  mov     [rsp+78h+var_48.changeUnitId.cbIdSize], ax
0x180007089  xor     eax, eax
0x18000708b  mov     word ptr [rsp+78h+var_48.changeUnitId+6], ax
0x180007090  mov     [rsp+78h+var_48.dwSize], 1Ch
0x180007098  call    ?CreateSyncKnowledge@KnowledgeServices@@SAJAEBU_ID_PARAMETERS@@_KPEAUIReplicaKeyMap@@PEAPEAUISyncKnowledge@@@Z; KnowledgeServices::CreateSyncKnowledge(_ID_PARAMETERS const &,unsigned __int64,IReplicaKeyMap *,ISyncKnowledge * *)
0x18000709d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070a4  mov     ebx, eax
0x1800070a6  jmp     loc_180007022
0x1800070ab  cmp     byte ptr [rcx+19h], 5
0x1800070af  jb      loc_180007014
0x1800070b5  mov     rcx, [rcx+10h]
0x1800070b9  lea     r9, aCsyncservicesC_10; "CSyncServices::CreateSyncKnowledge"
0x1800070c0  mov     edx, 1Eh
0x1800070c5  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x1800070cc  call    WPP_SF_s
0x1800070d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070d8  jmp     loc_180007014
0x1800070dd  cmp     byte ptr [rcx+19h], 5
0x1800070e1  jb      loc_180007031
0x1800070e7  mov     rcx, [rcx+10h]
0x1800070eb  lea     r9, aCsyncservicesC_10; "CSyncServices::CreateSyncKnowledge"
0x1800070f2  mov     edx, 1Fh
0x1800070f7  mov     [rsp+78h+var_58], ebx
0x1800070fb  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x180007102  call    WPP_SF_sD
0x180007107  jmp     loc_180007031
```
