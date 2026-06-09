# DafBthSyncRemoveAep(ushort *)

- ea: `0x180020dec`
- end: `0x180020fb9`
- name: `?DafBthSyncRemoveAep@@YAJPEAG@Z`
- size: `461`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002103c`

## callees

- `0x180020dec`
- `0x180021ac8`
- `0x180021b88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020e4d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020e4d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020f22`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f5f`
- `deviceassociation!DafCloseAssociationContext` at `0x180020f3c`
- `deviceassociation!DafCloseAssociationContext` at `0x180020f3c`
- `deviceassociation!DafStartRemoveAssociation` at `0x180020ef5`
- `deviceassociation!DafStartRemoveAssociation` at `0x180020ef5`
- `deviceassociation!DafCreateAssociationContext` at `0x180020ebb`
- `deviceassociation!DafCreateAssociationContext` at `0x180020ebb`

## pseudocode

```c
__int64 __fastcall DafBthSyncRemoveAep(unsigned __int16 *a1)
{
  signed int LastError; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  signed int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  bool v9; // cf
  HANDLE hHandle; // [rsp+48h] [rbp+10h] BYREF
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  hHandle = 0;
  v12 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( hHandle )
  {
    v5 = DafCreateAssociationContext(a1, 0, 0, 0, &v12);
    if ( v5 >= 0 )
    {
      v5 = DafStartRemoveAssociation(v12, DafBthSyncRemoveAepComplete, &hHandle);
      if ( v5 >= 0 )
      {
        WaitForSingleObject(hHandle, 0xFFFFFFFF);
        goto LABEL_20;
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 42;
        goto LABEL_10;
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 41;
        goto LABEL_10;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 40;
LABEL_10:
      WPP_SF_sd(v6[2], v7, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
LABEL_20:
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( v12 )
  {
    DafCloseAssociationContext(v12, v3, v4);
    v6 = WPP_GLOBAL_Control;
    v12 = 0;
  }
  if ( hHandle )
  {
    CloseHandle(hHandle);
    v6 = WPP_GLOBAL_Control;
    hHandle = 0;
  }
  v8 = 0;
  if ( v5 )
    v9 = *((_BYTE *)v6 + 25) < 2u;
  else
    v9 = *((_BYTE *)v6 + 25) < 5u;
  if ( v6 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v8) = !v9;
    if ( v8 )
      WPP_SF_sd(v6[2], 43, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020dec  mov     rax, rsp
0x180020def  mov     [rax+8], rbx
0x180020df3  mov     [rax+20h], rsi
0x180020df7  push    r14
0x180020df9  sub     rsp, 30h
0x180020dfd  mov     rbx, rcx
0x180020e00  mov     qword ptr [rax+10h], 0
0x180020e08  mov     qword ptr [rax+18h], 0
0x180020e10  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e17  lea     rsi, WPP_GLOBAL_Control
0x180020e1e  lea     r14, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180020e25  cmp     rcx, rsi
0x180020e28  jz      short loc_180020E41
0x180020e2a  cmp     byte ptr [rcx+19h], 5
0x180020e2e  jb      short loc_180020E41
0x180020e30  mov     rcx, [rcx+10h]
0x180020e34  mov     edx, 27h ; '''
0x180020e39  mov     r8, r14
0x180020e3c  call    WPP_SF_s
0x180020e41  xor     r9d, r9d; lpName
0x180020e44  xor     r8d, r8d; bInitialState
0x180020e47  xor     ecx, ecx; lpEventAttributes
0x180020e49  lea     edx, [r9+1]; bManualReset
0x180020e4d  call    cs:__imp_CreateEventW
0x180020e53  mov     [rsp+38h+hHandle], rax
0x180020e58  test    rax, rax
0x180020e5b  jnz     short loc_180020EA6
0x180020e5d  call    cs:__imp_GetLastError
0x180020e63  mov     ebx, eax
0x180020e65  test    eax, eax
0x180020e67  jle     short loc_180020E72
0x180020e69  movzx   ebx, ax
0x180020e6c  or      ebx, 80070000h
0x180020e72  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e79  cmp     rcx, rsi
0x180020e7c  jz      loc_180020F2F
0x180020e82  cmp     byte ptr [rcx+19h], 2
0x180020e86  jb      loc_180020F2F
0x180020e8c  mov     edx, 28h ; '('
0x180020e91  mov     dword ptr [rsp+38h+var_18], ebx
0x180020e95  mov     rcx, [rcx+10h]
0x180020e99  mov     r8, r14
0x180020e9c  call    WPP_SF_sd
0x180020ea1  jmp     loc_180020F28
0x180020ea6  lea     rax, [rsp+38h+arg_10]
0x180020eab  xor     r9d, r9d
0x180020eae  xor     r8d, r8d
0x180020eb1  mov     [rsp+38h+var_18], rax
0x180020eb6  xor     edx, edx
0x180020eb8  mov     rcx, rbx
0x180020ebb  call    cs:__imp_DafCreateAssociationContext
0x180020ec1  mov     ebx, eax
0x180020ec3  test    eax, eax
0x180020ec5  jns     short loc_180020EE4
0x180020ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ece  cmp     rcx, rsi
0x180020ed1  jz      short loc_180020F2F
0x180020ed3  cmp     byte ptr [rcx+19h], 2
0x180020ed7  jb      short loc_180020F2F
0x180020ed9  mov     edx, 29h ; ')'
0x180020ede  mov     dword ptr [rsp+38h+var_18], eax
0x180020ee2  jmp     short loc_180020E95
0x180020ee4  mov     rcx, [rsp+38h+arg_10]
0x180020ee9  lea     r8, [rsp+38h+hHandle]
0x180020eee  lea     rdx, ?DafBthSyncRemoveAepComplete@@YAXPEAXJ@Z; DafBthSyncRemoveAepComplete(void *,long)
0x180020ef5  call    cs:__imp_DafStartRemoveAssociation
0x180020efb  mov     ebx, eax
0x180020efd  test    eax, eax
0x180020eff  jns     short loc_180020F1A
0x180020f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f08  cmp     rcx, rsi
0x180020f0b  jz      short loc_180020F2F
0x180020f0d  cmp     byte ptr [rcx+19h], 2
0x180020f11  jb      short loc_180020F2F
0x180020f13  mov     edx, 2Ah ; '*'
0x180020f18  jmp     short loc_180020EDE
0x180020f1a  mov     rcx, [rsp+38h+hHandle]; hHandle
0x180020f1f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180020f22  call    cs:__imp_WaitForSingleObject
0x180020f28  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f2f  mov     rax, [rsp+38h+arg_10]
0x180020f34  test    rax, rax
0x180020f37  jz      short loc_180020F52
0x180020f39  mov     rcx, rax
0x180020f3c  call    cs:__imp_DafCloseAssociationContext
0x180020f42  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f49  mov     [rsp+38h+arg_10], 0
0x180020f52  mov     rax, [rsp+38h+hHandle]
0x180020f57  test    rax, rax
0x180020f5a  jz      short loc_180020F75
0x180020f5c  mov     rcx, rax; hObject
0x180020f5f  call    cs:__imp_CloseHandle
0x180020f65  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f6c  mov     [rsp+38h+hHandle], 0
0x180020f75  xor     eax, eax
0x180020f77  test    ebx, ebx
0x180020f79  jnz     short loc_180020F81
0x180020f7b  cmp     byte ptr [rcx+19h], 5
0x180020f7f  jmp     short loc_180020F85
0x180020f81  cmp     byte ptr [rcx+19h], 2
0x180020f85  setnb   al
0x180020f88  cmp     rcx, rsi
0x180020f8b  jz      short loc_180020FA6
0x180020f8d  test    eax, eax
0x180020f8f  jz      short loc_180020FA6
0x180020f91  mov     rcx, [rcx+10h]
0x180020f95  mov     edx, 2Bh ; '+'
0x180020f9a  mov     r8, r14
0x180020f9d  mov     dword ptr [rsp+38h+var_18], ebx
0x180020fa1  call    WPP_SF_sd
0x180020fa6  mov     rsi, [rsp+38h+arg_18]
0x180020fab  mov     eax, ebx
0x180020fad  mov     rbx, [rsp+38h+arg_0]
0x180020fb2  add     rsp, 30h
0x180020fb6  pop     r14
0x180020fb8  retn
```
