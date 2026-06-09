# CProtocolHandler::GetWitnessNodeInformation(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,uchar *,ulong *)

- ea: `0x180030ff0`
- end: `0x1800310c3`
- name: `?GetWitnessNodeInformation@CProtocolHandler@@QEAAKV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEAEPEAK@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030600`

## callees

- `0x18001c0e0`
- `0x18001e420`
- `0x180030ff0`
- `0x180031b00`
- `0x1800320a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031094`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031094`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031030`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031030`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProtocolHandler::GetWitnessNodeInformation(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  CProtocolHandler *v8; // rsi
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rax
  CClusterConnection *v12; // rcx
  unsigned int WitnessNodeInformation; // ebx
  _BYTE v15[8]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v16; // [rsp+28h] [rbp-40h]

  v16 = a2;
  v8 = WitnessProtocolHandler;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)WitnessProtocolHandler + 10));
  v9 = (__int64 *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(
                    (char *)v8 + 8,
                    v15,
                    a2);
  v10 = *v9;
  if ( *v9 == *((_QWORD *)v8 + 1)
    && (v11 = (__int64 *)std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(
                           (char *)v8 + 40,
                           v15,
                           a2),
        v10 = *v11,
        *v11 == *((_QWORD *)v8 + 5))
    || (v12 = *(CClusterConnection **)(v10 + 64)) == 0 )
  {
    WitnessNodeInformation = 1168;
    *a5 = 0;
  }
  else
  {
    WitnessNodeInformation = CClusterConnection::GetWitnessNodeInformation(v12, a3, a4, a5);
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)v8 + 10));
  std::wstring::~wstring(a2);
  return WitnessNodeInformation;
}

```

## disassembly

```asm
0x180030ff0  mov     [rsp+arg_0], rbx
0x180030ff5  push    rbp
0x180030ff6  push    rsi
0x180030ff7  push    rdi
0x180030ff8  push    r14
0x180030ffa  push    r15
0x180030ffc  sub     rsp, 40h
0x180031000  mov     rax, cs:__security_cookie
0x180031007  xor     rax, rsp
0x18003100a  mov     [rsp+68h+var_38], rax
0x18003100f  mov     r15, r9
0x180031012  mov     ebp, r8d
0x180031015  mov     rdi, rdx
0x180031018  mov     [rsp+68h+var_40], rdx
0x18003101d  mov     r14, [rsp+68h+arg_20]
0x180031025  mov     rsi, cs:?WitnessProtocolHandler@@3PEAVCProtocolHandler@@EA; CProtocolHandler * WitnessProtocolHandler
0x18003102c  mov     rcx, [rsi+50h]; lpCriticalSection
0x180031030  call    cs:__imp_EnterCriticalSection
0x180031036  mov     r8, rdi
0x180031039  lea     rdx, [rsp+68h+var_48]
0x18003103e  lea     rcx, [rsi+8]
0x180031042  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x180031047  mov     rcx, [rax]
0x18003104a  cmp     rcx, [rsi+8]
0x18003104e  jnz     short loc_18003106A
0x180031050  mov     r8, rdi
0x180031053  lea     rdx, [rsp+68h+var_48]
0x180031058  lea     rcx, [rsi+28h]
0x18003105c  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::find(std::wstring const &)
0x180031061  mov     rcx, [rax]
0x180031064  cmp     rcx, [rsi+28h]
0x180031068  jz      short loc_180031084
0x18003106a  mov     rcx, [rcx+40h]; this
0x18003106e  test    rcx, rcx
0x180031071  jz      short loc_180031084
0x180031073  mov     r9, r14; unsigned int *
0x180031076  mov     r8, r15; unsigned __int8 *
0x180031079  mov     edx, ebp; unsigned int
0x18003107b  call    ?GetWitnessNodeInformation@CClusterConnection@@QEAAKKPEAEPEAK@Z; CClusterConnection::GetWitnessNodeInformation(ulong,uchar *,ulong *)
0x180031080  mov     ebx, eax
0x180031082  jmp     short loc_180031090
0x180031084  mov     ebx, 490h
0x180031089  mov     dword ptr [r14], 0
0x180031090  mov     rcx, [rsi+50h]; lpCriticalSection
0x180031094  call    cs:__imp_LeaveCriticalSection
0x18003109a  nop
0x18003109b  mov     rcx, rdi
0x18003109e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800310a3  mov     eax, ebx
0x1800310a5  mov     rcx, [rsp+68h+var_38]
0x1800310aa  xor     rcx, rsp; StackCookie
0x1800310ad  call    __security_check_cookie
0x1800310b2  mov     rbx, [rsp+68h+arg_0]
0x1800310b7  add     rsp, 40h
0x1800310bb  pop     r15
0x1800310bd  pop     r14
0x1800310bf  pop     rdi
0x1800310c0  pop     rsi
0x1800310c1  pop     rbp
0x1800310c2  retn
```
