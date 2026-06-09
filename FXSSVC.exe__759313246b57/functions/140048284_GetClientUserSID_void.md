# GetClientUserSID(void)

- ea: `0x140048284`
- end: `0x1400483cc`
- name: `?GetClientUserSID@@YAPEAXXZ`
- size: `328`
- prototype: `void *(void)`
- caller_count: `16`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000fab0`
- `0x1400118e4`
- `0x140011fa0`
- `0x140012814`
- `0x140013004`
- `0x1400135d0`
- `0x140016690`
- `0x1400173d0`
- `0x140017f50`
- `0x14001a3c0`
- `0x14001ad20`
- `0x14001b190`
- `0x14001dbc0`
- `0x14001fe30`
- `0x140021e70`
- `0x140022460`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140048284`
- `0x14006998c`
- `0x140077e50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004832d`
- `KERNEL32!GetLastError` at `0x14004832d`
- `KERNEL32!SetLastError` at `0x14004830d`
- `KERNEL32!SetLastError` at `0x14004830d`
- `RPCRT4!RpcRevertToSelf` at `0x140048367`
- `RPCRT4!RpcRevertToSelf` at `0x140048367`
- `RPCRT4!RpcImpersonateClient` at `0x1400482c9`
- `RPCRT4!RpcImpersonateClient` at `0x1400482c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *GetClientUserSID(void)
{
  unsigned int v0; // eax
  DWORD v1; // ebx
  DWORD v2; // ecx
  void *CurrentThreadSID; // rbx
  DWORD LastError; // eax
  unsigned int v6; // eax
  DWORD v7; // edi

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
  }
  v0 = RpcImpersonateClient(0);
  v1 = v0;
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v0);
    }
    v2 = v1;
LABEL_11:
    SetLastError(v2);
    return 0;
  }
  CurrentThreadSID = (void *)GetCurrentThreadSID();
  if ( !CurrentThreadSID )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    }
  }
  v6 = RpcRevertToSelf();
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v6);
    }
    pMemFree(CurrentThreadSID);
    v2 = v7;
    goto LABEL_11;
  }
  return CurrentThreadSID;
}

```

## disassembly

```asm
0x140048284  mov     [rsp+arg_0], rbx
0x140048289  mov     [rsp+arg_8], rbp
0x14004828e  push    rdi
0x14004828f  sub     rsp, 20h
0x140048293  mov     rcx, cs:WPP_GLOBAL_Control
0x14004829a  lea     rbp, WPP_GLOBAL_Control
0x1400482a1  cmp     rcx, rbp
0x1400482a4  jz      short loc_1400482C7
0x1400482a6  test    byte ptr [rcx+1Ch], 4
0x1400482aa  jz      short loc_1400482C7
0x1400482ac  cmp     byte ptr [rcx+19h], 5
0x1400482b0  jb      short loc_1400482C7
0x1400482b2  mov     rcx, [rcx+10h]
0x1400482b6  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x1400482bd  mov     edx, 59h ; 'Y'
0x1400482c2  call    WPP_SF_
0x1400482c7  xor     ecx, ecx; BindingHandle
0x1400482c9  call    cs:__imp_RpcImpersonateClient
0x1400482d0  nop     dword ptr [rax+rax+00h]
0x1400482d5  mov     ebx, eax
0x1400482d7  test    eax, eax
0x1400482d9  jz      short loc_140048320
0x1400482db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400482e2  cmp     rcx, rbp
0x1400482e5  jz      short loc_14004830B
0x1400482e7  test    byte ptr [rcx+1Ch], 4
0x1400482eb  jz      short loc_14004830B
0x1400482ed  cmp     byte ptr [rcx+19h], 2
0x1400482f1  jb      short loc_14004830B
0x1400482f3  mov     rcx, [rcx+10h]
0x1400482f7  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x1400482fe  mov     edx, 5Ah ; 'Z'
0x140048303  mov     r9d, eax
0x140048306  call    WPP_SF_d
0x14004830b  mov     ecx, ebx; dwErrCode
0x14004830d  call    cs:__imp_SetLastError
0x140048314  nop     dword ptr [rax+rax+00h]
0x140048319  xor     eax, eax
0x14004831b  jmp     loc_1400483BB
0x140048320  call    GetCurrentThreadSID
0x140048325  mov     rbx, rax
0x140048328  test    rax, rax
0x14004832b  jnz     short loc_140048367
0x14004832d  call    cs:__imp_GetLastError
0x140048334  nop     dword ptr [rax+rax+00h]
0x140048339  mov     rcx, cs:WPP_GLOBAL_Control
0x140048340  cmp     rcx, rbp
0x140048343  jz      short loc_140048367
0x140048345  test    byte ptr [rcx+1Ch], 4
0x140048349  jz      short loc_140048367
0x14004834b  cmp     byte ptr [rcx+19h], 2
0x14004834f  jb      short loc_140048367
0x140048351  mov     rcx, [rcx+10h]
0x140048355  lea     edx, [rbx+5Bh]
0x140048358  mov     r9d, eax
0x14004835b  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140048362  call    WPP_SF_d
0x140048367  call    cs:__imp_RpcRevertToSelf
0x14004836e  nop     dword ptr [rax+rax+00h]
0x140048373  mov     edi, eax
0x140048375  test    eax, eax
0x140048377  jz      short loc_1400483B8
0x140048379  mov     rcx, cs:WPP_GLOBAL_Control
0x140048380  cmp     rcx, rbp
0x140048383  jz      short loc_1400483A9
0x140048385  test    byte ptr [rcx+1Ch], 4
0x140048389  jz      short loc_1400483A9
0x14004838b  cmp     byte ptr [rcx+19h], 2
0x14004838f  jb      short loc_1400483A9
0x140048391  mov     rcx, [rcx+10h]
0x140048395  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x14004839c  mov     edx, 5Ch ; '\'
0x1400483a1  mov     r9d, eax
0x1400483a4  call    WPP_SF_d
0x1400483a9  mov     rcx, rbx; lpMem
0x1400483ac  call    pMemFree
0x1400483b1  mov     ecx, edi
0x1400483b3  jmp     loc_14004830D
0x1400483b8  mov     rax, rbx
0x1400483bb  mov     rbx, [rsp+28h+arg_0]
0x1400483c0  mov     rbp, [rsp+28h+arg_8]
0x1400483c5  add     rsp, 20h
0x1400483c9  pop     rdi
0x1400483ca  retn
```
