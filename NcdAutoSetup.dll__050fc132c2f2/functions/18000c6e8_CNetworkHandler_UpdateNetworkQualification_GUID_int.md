# CNetworkHandler::UpdateNetworkQualification(_GUID,int)

- ea: `0x18000c6e8`
- end: `0x18000c83b`
- name: `?UpdateNetworkQualification@CNetworkHandler@@QEAAJU_GUID@@H@Z`
- size: `339`
- prototype: `__int64 __fastcall(CNetworkHandler *__hidden this, struct _GUID *__struct_ptr, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c850`

## callees

- `0x1800074f0`
- `0x18000a644`
- `0x18000c6e8`
- `0x1800113bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c7c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c7c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c760`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c760`

## pseudocode

```c
__int64 __fastcall CNetworkHandler::UpdateNetworkQualification(CNetworkHandler *this, struct _GUID *a2, int a3)
{
  _QWORD *v6; // rcx
  int v7; // esi
  int v8; // edi
  int v9; // r14d
  __int64 *i; // rcx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // ecx
  unsigned int restarted; // eax
  unsigned int v16; // ebx

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = 0;
  v8 = 0;
  v9 = 0;
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_(v6[2], 63, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  for ( i = (__int64 *)*((_QWORD *)this + 10); i != (__int64 *)((char *)this + 80); i = (__int64 *)*i )
  {
    if ( i[2] == *(_QWORD *)&a2->Data1 && i[3] == *(_QWORD *)a2->Data4 )
    {
      if ( *((_DWORD *)i + 9) == a3 )
        break;
      *((_DWORD *)i + 9) = a3;
      v11 = *((_DWORD *)this + 10);
      if ( a3 )
      {
        v12 = v11 + 1;
        v9 = 1;
        *((_DWORD *)this + 10) = v12;
        if ( v12 == 1 )
          v7 = 1;
      }
      else
      {
        v13 = v11 - 1;
        *((_DWORD *)this + 10) = v13;
        if ( !v13 )
          v8 = 1;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( v7 )
  {
    v14 = 1;
LABEL_20:
    restarted = SMTransition(v14);
LABEL_26:
    v16 = restarted;
    goto LABEL_27;
  }
  if ( v8 )
  {
    v14 = 2;
    goto LABEL_20;
  }
  v16 = 0;
  if ( v9 && Block )
  {
    restarted = CDeviceHandler::RestartDiscovery(Block);
    goto LABEL_26;
  }
LABEL_27:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids);
  return v16;
}

```

## disassembly

```asm
0x18000c6e8  push    rbx
0x18000c6ea  push    rbp
0x18000c6eb  push    rsi
0x18000c6ec  push    rdi
0x18000c6ed  push    r12
0x18000c6ef  push    r13
0x18000c6f1  push    r14
0x18000c6f3  push    r15
0x18000c6f5  sub     rsp, 28h
0x18000c6f9  mov     ebp, r8d
0x18000c6fc  mov     r12, rdx
0x18000c6ff  mov     rbx, rcx
0x18000c702  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c709  lea     r15, WPP_GLOBAL_Control
0x18000c710  cmp     rcx, r15
0x18000c713  jz      short loc_18000C737
0x18000c715  test    byte ptr [rcx+1Ch], 20h
0x18000c719  jz      short loc_18000C737
0x18000c71b  mov     rcx, [rcx+10h]
0x18000c71f  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000c726  mov     edx, 3Eh ; '>'
0x18000c72b  call    WPP_SF_
0x18000c730  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c737  xor     esi, esi
0x18000c739  xor     edi, edi
0x18000c73b  xor     r14d, r14d
0x18000c73e  cmp     rcx, r15
0x18000c741  jz      short loc_18000C75C
0x18000c743  test    byte ptr [rcx+1Ch], 8
0x18000c747  jz      short loc_18000C75C
0x18000c749  mov     rcx, [rcx+10h]
0x18000c74d  lea     edx, [rsi+3Fh]
0x18000c750  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000c757  call    WPP_SF_
0x18000c75c  lea     rcx, [rbx+60h]; lpCriticalSection
0x18000c760  call    cs:__imp_EnterCriticalSection
0x18000c766  lea     rdx, [rbx+50h]
0x18000c76a  mov     r13d, 1
0x18000c770  mov     rcx, [rdx]
0x18000c773  jmp     short loc_18000C7B8
0x18000c775  mov     rax, [rcx+10h]
0x18000c779  cmp     rax, [r12]
0x18000c77d  jnz     short loc_18000C7B5
0x18000c77f  mov     rax, [rcx+18h]
0x18000c783  cmp     rax, [r12+8]
0x18000c788  jnz     short loc_18000C7B5
0x18000c78a  cmp     [rcx+24h], ebp
0x18000c78d  jz      short loc_18000C7BD
0x18000c78f  mov     [rcx+24h], ebp
0x18000c792  mov     eax, [rbx+28h]
0x18000c795  test    ebp, ebp
0x18000c797  jz      short loc_18000C7AB
0x18000c799  inc     eax
0x18000c79b  mov     r14d, r13d
0x18000c79e  mov     [rbx+28h], eax
0x18000c7a1  cmp     eax, r13d
0x18000c7a4  jnz     short loc_18000C7B5
0x18000c7a6  mov     esi, r13d
0x18000c7a9  jmp     short loc_18000C7B5
0x18000c7ab  sub     eax, r13d
0x18000c7ae  mov     [rbx+28h], eax
0x18000c7b1  cmovz   edi, r13d
0x18000c7b5  mov     rcx, [rcx]
0x18000c7b8  cmp     rcx, rdx
0x18000c7bb  jnz     short loc_18000C775
0x18000c7bd  lea     rcx, [rbx+60h]; lpCriticalSection
0x18000c7c1  call    cs:__imp_LeaveCriticalSection
0x18000c7c7  test    esi, esi
0x18000c7c9  jz      short loc_18000C7D5
0x18000c7cb  mov     ecx, r13d
0x18000c7ce  call    ?SMTransition@@YAJW4NCDAS_TRIGGER@@@Z; SMTransition(NCDAS_TRIGGER)
0x18000c7d3  jmp     short loc_18000C7F8
0x18000c7d5  test    edi, edi
0x18000c7d7  jz      short loc_18000C7E0
0x18000c7d9  mov     ecx, 2
0x18000c7de  jmp     short loc_18000C7CE
0x18000c7e0  xor     ebx, ebx
0x18000c7e2  test    r14d, r14d
0x18000c7e5  jz      short loc_18000C7FA
0x18000c7e7  mov     rcx, qword ptr cs:Block; this
0x18000c7ee  test    rcx, rcx
0x18000c7f1  jz      short loc_18000C7FA
0x18000c7f3  call    ?RestartDiscovery@CDeviceHandler@@QEAAJXZ; CDeviceHandler::RestartDiscovery(void)
0x18000c7f8  mov     ebx, eax
0x18000c7fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c801  lea     rax, WPP_GLOBAL_Control
0x18000c808  cmp     rcx, rax
0x18000c80b  jz      short loc_18000C828
0x18000c80d  test    byte ptr [rcx+1Ch], 20h
0x18000c811  jz      short loc_18000C828
0x18000c813  mov     rcx, [rcx+10h]
0x18000c817  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids
0x18000c81e  mov     edx, 40h ; '@'
0x18000c823  call    WPP_SF_
0x18000c828  mov     eax, ebx
0x18000c82a  add     rsp, 28h
0x18000c82e  pop     r15
0x18000c830  pop     r14
0x18000c832  pop     r13
0x18000c834  pop     r12
0x18000c836  pop     rdi
0x18000c837  pop     rsi
0x18000c838  pop     rbp
0x18000c839  pop     rbx
0x18000c83a  retn
```
