# SyncKnowledge::RemoveAllChangeUnitsRequiredMarker(uchar *)

- ea: `0x180086f60`
- end: `0x18008709c`
- name: `?RemoveAllChangeUnitsRequiredMarker@SyncKnowledge@@UEAAJPEAE@Z`
- size: `316`
- prototype: `int(SyncKnowledge *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18000bde0`
- `0x180011bb0`
- `0x180011f60`
- `0x18001a038`
- `0x18001ae20`
- `0x180086f60`
- `0x18008a268`

## string_xrefs

- `0x180086f96`: `SyncKnowledge::RemoveAllChangeUnitsRequiredMarker`
- `0x180087067`: `SyncKnowledge::RemoveAllChangeUnitsRequiredMarker`

## pseudocode

```c
__int64 __fastcall SyncKnowledge::RemoveAllChangeUnitsRequiredMarker(SyncKnowledge *this, unsigned __int8 *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // eax
  int v8; // eax
  _BYTE v10[4]; // [rsp+30h] [rbp-48h] BYREF
  int v11; // [rsp+34h] [rbp-44h]
  __int64 v12; // [rsp+38h] [rbp-40h]
  int v13; // [rsp+90h] [rbp+18h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      100,
      WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids,
      "SyncKnowledge::RemoveAllChangeUnitsRequiredMarker");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)this + 160) & 1) != 0 )
  {
    v6 = KnowledgeServices::ValidateIdBytes((SyncKnowledge *)((char *)this + 48), a2);
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v5 = v6;
  }
  else
  {
    v5 = -2147217379;
  }
  v11 = 0;
  v12 = 0;
  if ( !v5 )
  {
    v7 = SyncId::Initialize((SyncId *)v10, (SyncKnowledge *)((char *)this + 48), a2);
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v5 = v7;
  }
  v13 = 0;
  if ( !v5 )
  {
    v8 = MarkerManager::RemoveMarker((SyncKnowledge *)((char *)this + 272), 1, (const struct SyncId *)v10, &v13);
    v4 = (PVOID *)WPP_GLOBAL_Control;
    v5 = v8;
    if ( !v8 )
      v5 = v13 == 0;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      101,
      (unsigned int)WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids,
      (unsigned int)"SyncKnowledge::RemoveAllChangeUnitsRequiredMarker",
      v5);
  SyncId::~SyncId((SyncId *)v10);
  return v5;
}

```

## disassembly

```asm
0x180086f60  push    rbx
0x180086f62  push    rbp
0x180086f63  push    rsi
0x180086f64  push    rdi
0x180086f65  push    r12
0x180086f67  push    r15
0x180086f69  sub     rsp, 48h
0x180086f6d  mov     rbp, rdx
0x180086f70  mov     rsi, rcx
0x180086f73  mov     rcx, cs:WPP_GLOBAL_Control
0x180086f7a  lea     r12, WPP_GLOBAL_Control
0x180086f81  cmp     rcx, r12
0x180086f84  jz      short loc_180086FB5
0x180086f86  test    byte ptr [rcx+1Ch], 40h
0x180086f8a  jz      short loc_180086FB5
0x180086f8c  cmp     byte ptr [rcx+19h], 5
0x180086f90  jb      short loc_180086FB5
0x180086f92  mov     rcx, [rcx+10h]
0x180086f96  lea     r9, aSyncknowledgeR_0; "SyncKnowledge::RemoveAllChangeUnitsRequ"...
0x180086f9d  mov     edx, 64h ; 'd'
0x180086fa2  lea     r8, WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids
0x180086fa9  call    WPP_SF_s
0x180086fae  mov     rcx, cs:WPP_GLOBAL_Control
0x180086fb5  mov     r15d, 1
0x180086fbb  test    [rsi+0A0h], r15b
0x180086fc2  jnz     short loc_180086FCB
0x180086fc4  mov     ebx, 8004101Dh
0x180086fc9  jmp     short loc_180086FE0
0x180086fcb  mov     rdx, rbp; unsigned __int8 *
0x180086fce  lea     rcx, [rsi+30h]; struct IdFormat *
0x180086fd2  call    ?ValidateIdBytes@KnowledgeServices@@SAJAEBUIdFormat@@PEBE@Z; KnowledgeServices::ValidateIdBytes(IdFormat const &,uchar const *)
0x180086fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180086fde  mov     ebx, eax
0x180086fe0  mov     [rsp+78h+var_44], 0
0x180086fe8  mov     [rsp+78h+var_40], 0
0x180086ff1  test    ebx, ebx
0x180086ff3  jnz     short loc_18008700F
0x180086ff5  mov     r8, rbp; unsigned __int8 *
0x180086ff8  lea     rdx, [rsi+30h]; struct IdFormat *
0x180086ffc  lea     rcx, [rsp+78h+var_48]; this
0x180087001  call    ?Initialize@SyncId@@QEAAJAEBUIdFormat@@PEBE@Z; SyncId::Initialize(IdFormat const &,uchar const *)
0x180087006  mov     rcx, cs:WPP_GLOBAL_Control
0x18008700d  mov     ebx, eax
0x18008700f  mov     [rsp+78h+arg_10], 0
0x18008701a  test    ebx, ebx
0x18008701c  jnz     short loc_180087052
0x18008701e  lea     rcx, [rsi+110h]; this
0x180087025  mov     edx, r15d; int
0x180087028  lea     r9, [rsp+78h+arg_10]; int *
0x180087030  lea     r8, [rsp+78h+var_48]; struct SyncId *
0x180087035  call    ?RemoveMarker@MarkerManager@@QEAAJHAEBVSyncId@@AEAH@Z; MarkerManager::RemoveMarker(int,SyncId const &,int &)
0x18008703a  mov     rcx, cs:WPP_GLOBAL_Control
0x180087041  mov     ebx, eax
0x180087043  test    eax, eax
0x180087045  jnz     short loc_180087052
0x180087047  cmp     [rsp+78h+arg_10], eax
0x18008704e  cmovz   ebx, r15d
0x180087052  cmp     rcx, r12
0x180087055  jz      short loc_180087083
0x180087057  test    byte ptr [rcx+1Ch], 40h
0x18008705b  jz      short loc_180087083
0x18008705d  cmp     byte ptr [rcx+19h], 5
0x180087061  jb      short loc_180087083
0x180087063  mov     rcx, [rcx+10h]
0x180087067  lea     r9, aSyncknowledgeR_0; "SyncKnowledge::RemoveAllChangeUnitsRequ"...
0x18008706e  mov     edx, 65h ; 'e'
0x180087073  mov     [rsp+78h+var_58], ebx
0x180087077  lea     r8, WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids
0x18008707e  call    WPP_SF_sD
0x180087083  lea     rcx, [rsp+78h+var_48]; this
0x180087088  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18008708d  mov     eax, ebx
0x18008708f  add     rsp, 48h
0x180087093  pop     r15
0x180087095  pop     r12
0x180087097  pop     rdi
0x180087098  pop     rsi
0x180087099  pop     rbp
0x18008709a  pop     rbx
0x18008709b  retn
```
