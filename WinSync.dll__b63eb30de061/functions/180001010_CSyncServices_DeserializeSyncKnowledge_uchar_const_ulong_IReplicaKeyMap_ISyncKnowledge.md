# CSyncServices::DeserializeSyncKnowledge(uchar const *,ulong,IReplicaKeyMap *,ISyncKnowledge * *)

- ea: `0x180001010`
- end: `0x180001114`
- name: `?DeserializeSyncKnowledge@CSyncServices@@UEAAJPEBEKPEAUIReplicaKeyMap@@PEAPEAUISyncKnowledge@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(CSyncServices *this, const unsigned __int8 *, unsigned int, struct IReplicaKeyMap *, struct ISyncKnowledge **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18002d170`

## callees

- `0x180001010`
- `0x1800017ac`
- `0x18001a038`
- `0x18001ae20`

## string_xrefs

- `0x1800010c1`: `CSyncServices::DeserializeSyncKnowledge`
- `0x1800010f3`: `CSyncServices::DeserializeSyncKnowledge`

## pseudocode

```c
__int64 __fastcall CSyncServices::DeserializeSyncKnowledge(
        CSyncServices *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        struct IReplicaKeyMap *a4,
        struct ISyncKnowledge **a5)
{
  PVOID *v9; // rcx
  struct _ID_PARAMETER_PAIR *v10; // rdx
  unsigned int v11; // ebx
  int v13; // eax
  struct _ID_PARAMETER_PAIR v14; // [rsp+50h] [rbp+8h] BYREF

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::DeserializeSyncKnowledge");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = (struct _ID_PARAMETER_PAIR *)*((_QWORD *)this + 6);
  if ( v10 )
  {
    v14 = *v10;
    *(&v14.cbIdSize + 1) = 0;
    v13 = KnowledgeServices::DeserializeSyncKnowledge(&v14, a2, a3, a4, a5);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v11 = v13;
  }
  else
  {
    v11 = -2147217407;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      33,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::DeserializeSyncKnowledge",
      v11);
  return v11;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_8], rbx
0x180001015  mov     [rsp+arg_10], rbp
0x18000101a  push    rsi
0x18000101b  push    rdi
0x18000101c  push    r14
0x18000101e  sub     rsp, 30h
0x180001022  mov     rdi, r9
0x180001025  mov     esi, r8d
0x180001028  mov     rbp, rdx
0x18000102b  mov     rbx, rcx
0x18000102e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001035  lea     r14, WPP_GLOBAL_Control
0x18000103c  cmp     rcx, r14
0x18000103f  jz      short loc_180001047
0x180001041  test    byte ptr [rcx+1Ch], 2
0x180001045  jnz     short loc_1800010B7
0x180001047  mov     rdx, [rbx+30h]
0x18000104b  test    rdx, rdx
0x18000104e  jnz     short loc_180001079
0x180001050  mov     ebx, 80041001h
0x180001055  cmp     rcx, r14
0x180001058  jz      short loc_180001064
0x18000105a  test    byte ptr [rcx+1Ch], 2
0x18000105e  jnz     loc_1800010E5
0x180001064  mov     rbp, [rsp+48h+arg_10]
0x180001069  mov     eax, ebx
0x18000106b  mov     rbx, [rsp+48h+arg_8]
0x180001070  add     rsp, 30h
0x180001074  pop     r14
0x180001076  pop     rdi
0x180001077  pop     rsi
0x180001078  retn
0x180001079  mov     eax, [rdx]
0x18000107b  lea     rcx, [rsp+48h+arg_0]; struct _ID_PARAMETER_PAIR *
0x180001080  mov     [rsp+48h+arg_0.fIsVariable], eax
0x180001084  mov     r9, rdi; struct IReplicaKeyMap *
0x180001087  movzx   eax, word ptr [rdx+4]
0x18000108b  mov     r8d, esi; unsigned int
0x18000108e  mov     [rsp+48h+arg_0.cbIdSize], ax
0x180001093  mov     rdx, rbp; unsigned __int8 *
0x180001096  xor     eax, eax
0x180001098  mov     word ptr [rsp+48h+arg_0+6], ax
0x18000109d  mov     rax, [rsp+48h+arg_20]
0x1800010a2  mov     [rsp+48h+var_28], rax; struct ISyncKnowledge **
0x1800010a7  call    ?DeserializeSyncKnowledge@KnowledgeServices@@SAJAEBU_ID_PARAMETER_PAIR@@PEBEKPEAUIReplicaKeyMap@@PEAPEAUISyncKnowledge@@@Z; KnowledgeServices::DeserializeSyncKnowledge(_ID_PARAMETER_PAIR const &,uchar const *,ulong,IReplicaKeyMap *,ISyncKnowledge * *)
0x1800010ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800010b3  mov     ebx, eax
0x1800010b5  jmp     short loc_180001055
0x1800010b7  cmp     byte ptr [rcx+19h], 5
0x1800010bb  jb      short loc_180001047
0x1800010bd  mov     rcx, [rcx+10h]
0x1800010c1  lea     r9, aCsyncservicesD_2; "CSyncServices::DeserializeSyncKnowledge"
0x1800010c8  mov     edx, 20h ; ' '
0x1800010cd  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x1800010d4  call    WPP_SF_s
0x1800010d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800010e0  jmp     loc_180001047
0x1800010e5  cmp     byte ptr [rcx+19h], 5
0x1800010e9  jb      loc_180001064
0x1800010ef  mov     rcx, [rcx+10h]
0x1800010f3  lea     r9, aCsyncservicesD_2; "CSyncServices::DeserializeSyncKnowledge"
0x1800010fa  mov     edx, 21h ; '!'
0x1800010ff  mov     dword ptr [rsp+48h+var_28], ebx
0x180001103  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18000110a  call    WPP_SF_sD
0x18000110f  jmp     loc_180001064
```
