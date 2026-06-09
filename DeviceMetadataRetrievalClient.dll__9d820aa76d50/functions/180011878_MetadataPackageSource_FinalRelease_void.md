# MetadataPackageSource::FinalRelease(void)

- ea: `0x180011878`
- end: `0x1800119b8`
- name: `?FinalRelease@MetadataPackageSource@@QEAAXXZ`
- size: `320`
- prototype: `void __fastcall(MetadataPackageSource *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011310`
- `0x180011390`

## callees

- `0x180004d08`
- `0x180004d70`
- `0x180004dec`
- `0x180011878`
- `0x180013700`
- `0x180014010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800118dc`
- `KERNEL32!EnterCriticalSection` at `0x1800118dc`
- `KERNEL32!LeaveCriticalSection` at `0x180011942`
- `KERNEL32!LeaveCriticalSection` at `0x180011942`
- `KERNEL32!DeleteCriticalSection` at `0x1800118a3`
- `KERNEL32!DeleteCriticalSection` at `0x1800118a3`
- `ADVAPI32!EventUnregister` at `0x180011935`
- `ADVAPI32!EventUnregister` at `0x180011935`

## pseudocode

```c
void __fastcall MetadataPackageSource::FinalRelease(MetadataPackageSource *this)
{
  __int64 v2; // r8
  unsigned int v3; // ebx
  REGHANDLE v4; // rcx
  __int64 v5; // r8
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-28h] BYREF

  (*(void (__fastcall **)(MetadataPackageSource *))(*(_QWORD *)this + 40LL))(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(userpnp_Context, &DMRC_START_UNINITIALIZE, v2, 1u, &v6);
  EnterCriticalSection(&g_Crit);
  if ( qword_18001EAA8 )
  {
    v3 = 0;
    if ( !--qword_18001EAA8 )
      MrcExit();
  }
  else
  {
    v3 = 1;
  }
  v4 = RegHandle;
  dword_18001E2A0 = 0;
  RegHandle = 0;
  EventUnregister(v4);
  LeaveCriticalSection(&g_Crit);
  if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(userpnp_Context, &DMRC_STOP_UNINITIALIZE, v5, 1u, &v6);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_bab4a60a0f10308a353b12310872734a_Traceguids, v3);
}

```

## disassembly

```asm
0x180011878  push    rbx
0x18001187a  sub     rsp, 50h
0x18001187e  mov     rax, cs:__security_cookie
0x180011885  xor     rax, rsp
0x180011888  mov     [rsp+58h+var_18], rax
0x18001188d  mov     rax, [rcx]
0x180011890  mov     rbx, rcx
0x180011893  mov     rax, [rax+28h]
0x180011897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001189c  lea     rcx, [rbx+0B0h]; lpCriticalSection
0x1800118a3  call    cs:__imp_DeleteCriticalSection
0x1800118a9  test    cs:Microsoft_Windows_UserPnpEnableBits, 4
0x1800118b0  jz      short loc_1800118D5
0x1800118b2  lea     rax, [rsp+58h+var_28]
0x1800118b7  mov     r9d, 1
0x1800118bd  lea     rdx, DMRC_START_UNINITIALIZE
0x1800118c4  mov     [rsp+58h+var_38], rax
0x1800118c9  lea     rcx, userpnp_Context
0x1800118d0  call    McGenEventWrite_EventWriteTransfer
0x1800118d5  lea     rcx, ?g_Crit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800118dc  call    cs:__imp_EnterCriticalSection
0x1800118e2  mov     rax, cs:qword_18001EAA8
0x1800118e9  test    rax, rax
0x1800118ec  jz      short loc_180011914
0x1800118ee  mov     rax, cs:qword_18001EAA8
0x1800118f5  xor     ebx, ebx
0x1800118f7  dec     rax
0x1800118fa  mov     cs:qword_18001EAA8, rax
0x180011901  mov     rax, cs:qword_18001EAA8
0x180011908  test    rax, rax
0x18001190b  jnz     short loc_180011919
0x18001190d  call    _MrcExit
0x180011912  jmp     short loc_180011919
0x180011914  mov     ebx, 1
0x180011919  mov     rcx, cs:RegHandle; RegHandle
0x180011920  mov     cs:dword_18001E2A0, 0
0x18001192a  mov     cs:RegHandle, 0
0x180011935  call    cs:__imp_EventUnregister
0x18001193b  lea     rcx, ?g_Crit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011942  call    cs:__imp_LeaveCriticalSection
0x180011948  test    cs:Microsoft_Windows_UserPnpEnableBits, 4
0x18001194f  jz      short loc_180011974
0x180011951  lea     rax, [rsp+58h+var_28]
0x180011956  mov     r9d, 1
0x18001195c  lea     rdx, DMRC_STOP_UNINITIALIZE
0x180011963  mov     [rsp+58h+var_38], rax
0x180011968  lea     rcx, userpnp_Context
0x18001196f  call    McGenEventWrite_EventWriteTransfer
0x180011974  mov     rcx, cs:WPP_GLOBAL_Control
0x18001197b  lea     rax, WPP_GLOBAL_Control
0x180011982  cmp     rcx, rax
0x180011985  jz      short loc_1800119A5
0x180011987  test    byte ptr [rcx+1Ch], 8
0x18001198b  jz      short loc_1800119A5
0x18001198d  mov     rcx, [rcx+10h]
0x180011991  lea     r8, WPP_bab4a60a0f10308a353b12310872734a_Traceguids
0x180011998  mov     edx, 0Bh
0x18001199d  mov     r9d, ebx
0x1800119a0  call    WPP_SF_d
0x1800119a5  mov     rcx, [rsp+58h+var_18]
0x1800119aa  xor     rcx, rsp; StackCookie
0x1800119ad  call    __security_check_cookie
0x1800119b2  add     rsp, 50h
0x1800119b6  pop     rbx
0x1800119b7  retn
```
