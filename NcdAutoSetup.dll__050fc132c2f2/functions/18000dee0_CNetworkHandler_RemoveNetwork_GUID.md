# CNetworkHandler::_RemoveNetwork(_GUID)

- ea: `0x18000dee0`
- end: `0x18000e02f`
- name: `?_RemoveNetwork@CNetworkHandler@@AEAAJU_GUID@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(CNetworkHandler *this, struct _GUID *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bc10`

## callees

- `0x1800018c4`
- `0x18000a644`
- `0x18000dee0`
- `0x18000e28c`
- `0x1800113bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dfd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dfd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000df2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000df2c`

## pseudocode

```c
__int64 __fastcall CNetworkHandler::_RemoveNetwork(CNetworkHandler *this, struct _GUID *a2, __int64 a3)
{
  int v5; // esi
  CNetworkHandler **v6; // rbx
  CNetworkHandler *v7; // r12
  CNetworkHandler *v9; // rax
  CNetworkHandler **v10; // rcx
  CNetworkHandler *v11; // rcx
  unsigned int v12; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, a3, a2);
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v6 = (CNetworkHandler **)*((_QWORD *)this + 10);
  if ( v6 != (CNetworkHandler **)((char *)this + 80) )
  {
    do
    {
      v7 = *v6;
      if ( v6[2] == *(CNetworkHandler **)&a2->Data1 && v6[3] == *(CNetworkHandler **)a2->Data4 )
      {
        if ( *((_DWORD *)v6 + 9) )
        {
          if ( (*((_DWORD *)this + 10))-- == 1 )
            v5 = 1;
        }
        v9 = *v6;
        if ( *((CNetworkHandler ***)*v6 + 1) != v6 || (v10 = (CNetworkHandler **)v6[1], *v10 != (CNetworkHandler *)v6) )
          __fastfail(3u);
        *v10 = v9;
        *((_QWORD *)v9 + 1) = v10;
        v11 = v6[7];
        if ( v11 )
        {
          CoTaskMemFree(v11);
          v6[7] = 0;
        }
        v6[8] = 0;
        v6[9] = 0;
        operator delete(v6);
      }
      v6 = (CNetworkHandler **)v7;
    }
    while ( v7 != (CNetworkHandler *)((char *)this + 80) );
  }
  v12 = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( v5 )
    v12 = SMTransition(2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  return v12;
}

```

## disassembly

```asm
0x18000dee0  mov     [rsp+arg_10], rbx
0x18000dee5  mov     [rsp+arg_18], rbp
0x18000deea  push    rsi
0x18000deeb  push    rdi
0x18000deec  push    r12
0x18000deee  push    r14
0x18000def0  push    r15
0x18000def2  sub     rsp, 30h
0x18000def6  mov     rbp, rdx
0x18000def9  mov     rdi, rcx
0x18000defc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df03  lea     r12, WPP_GLOBAL_Control
0x18000df0a  cmp     rcx, r12
0x18000df0d  jz      short loc_18000DF26
0x18000df0f  test    byte ptr [rcx+1Ch], 20h
0x18000df13  jz      short loc_18000DF26
0x18000df15  mov     rcx, [rcx+10h]
0x18000df19  mov     edx, 8Ah
0x18000df1e  mov     r9, rbp
0x18000df21  call    WPP_SF__guid_
0x18000df26  lea     rcx, [rdi+60h]; lpCriticalSection
0x18000df2a  xor     esi, esi
0x18000df2c  call    cs:__imp_EnterCriticalSection
0x18000df32  lea     r14, [rdi+50h]
0x18000df36  mov     rbx, [r14]
0x18000df39  cmp     rbx, r14
0x18000df3c  jz      loc_18000DFCE
0x18000df42  mov     rax, [rbx+10h]
0x18000df46  mov     r12, [rbx]
0x18000df49  cmp     rax, [rbp+0]
0x18000df4d  jnz     short loc_18000DFBB
0x18000df4f  mov     rax, [rbx+18h]
0x18000df53  cmp     rax, [rbp+8]
0x18000df57  jnz     short loc_18000DFBB
0x18000df59  cmp     dword ptr [rbx+24h], 0
0x18000df5d  jz      short loc_18000DF6B
0x18000df5f  add     dword ptr [rdi+28h], 0FFFFFFFFh
0x18000df63  mov     eax, 1
0x18000df68  cmovz   esi, eax
0x18000df6b  mov     rax, [rbx]
0x18000df6e  cmp     [rax+8], rbx
0x18000df72  jnz     loc_18000E028
0x18000df78  mov     rcx, [rbx+8]
0x18000df7c  cmp     [rcx], rbx
0x18000df7f  jnz     loc_18000E028
0x18000df85  mov     [rcx], rax
0x18000df88  mov     [rax+8], rcx
0x18000df8c  mov     rcx, [rbx+38h]; pv
0x18000df90  test    rcx, rcx
0x18000df93  jz      short loc_18000DFA3
0x18000df95  call    cs:__imp_CoTaskMemFree
0x18000df9b  mov     qword ptr [rbx+38h], 0
0x18000dfa3  mov     rcx, rbx; Block
0x18000dfa6  mov     qword ptr [rbx+40h], 0
0x18000dfae  mov     qword ptr [rbx+48h], 0
0x18000dfb6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dfbb  mov     rbx, r12
0x18000dfbe  cmp     r12, r14
0x18000dfc1  jnz     loc_18000DF42
0x18000dfc7  lea     r12, WPP_GLOBAL_Control
0x18000dfce  lea     rcx, [rdi+60h]; lpCriticalSection
0x18000dfd2  xor     ebx, ebx
0x18000dfd4  call    cs:__imp_LeaveCriticalSection
0x18000dfda  test    esi, esi
0x18000dfdc  jz      short loc_18000DFE8
0x18000dfde  lea     ecx, [rbx+2]
0x18000dfe1  call    ?SMTransition@@YAJW4NCDAS_TRIGGER@@@Z; SMTransition(NCDAS_TRIGGER)
0x18000dfe6  mov     ebx, eax
0x18000dfe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfef  cmp     rcx, r12
0x18000dff2  jz      short loc_18000E00F
0x18000dff4  test    byte ptr [rcx+1Ch], 20h
0x18000dff8  jz      short loc_18000E00F
0x18000dffa  mov     rcx, [rcx+10h]
0x18000dffe  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000e005  mov     edx, 8Bh
0x18000e00a  call    WPP_SF_
0x18000e00f  mov     rbp, [rsp+58h+arg_18]
0x18000e014  mov     eax, ebx
0x18000e016  mov     rbx, [rsp+58h+arg_10]
0x18000e01b  add     rsp, 30h
0x18000e01f  pop     r15
0x18000e021  pop     r14
0x18000e023  pop     r12
0x18000e025  pop     rdi
0x18000e026  pop     rsi
0x18000e027  retn
0x18000e028  mov     ecx, 3
0x18000e02d  int     29h; Win8: RtlFailFast(ecx)
```
