# InitializeJobManager(_REG_FAX_SERVICE *)

- ea: `0x14003417c`
- end: `0x1400342a8`
- name: `?InitializeJobManager@@YAHPEAU_REG_FAX_SERVICE@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(struct _REG_FAX_SERVICE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140049f40`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x14003417c`
- `0x1400699d0`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400341f6`
- `KERNEL32!GetLastError` at `0x140034260`
- `KERNEL32!GetLastError` at `0x1400341f6`
- `KERNEL32!GetLastError` at `0x140034260`
- `KERNEL32!CreateIoCompletionPort` at `0x1400341da`
- `KERNEL32!CreateIoCompletionPort` at `0x1400341da`

## pseudocode

```c
__int64 __fastcall InitializeJobManager(struct _REG_FAX_SERVICE *a1)
{
  unsigned int v1; // ebx
  int v2; // eax
  unsigned __int16 *v3; // rdx
  DWORD v4; // eax
  DWORD LastError; // [rsp+30h] [rbp-38h]
  unsigned __int16 v7[14]; // [rsp+34h] [rbp-34h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  v1 = 1;
  g_StatusCompletionPortHandle = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u);
  if ( !g_StatusCompletionPortHandle )
  {
    LastError = GetLastError();
    v7[0] = 0;
    v2 = StringCchPrintfW(v7, 0xCu, L"%ld", LastError);
    v3 = v7;
    if ( v2 < 0 )
      LOBYTE(v3) = 0;
    FaxLog(1u, 1u, 1u, 0xC0007D2C, (char)v3);
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v4);
    }
    return 0;
  }
  return v1;
}

```

## disassembly

```asm
0x14003417c  mov     [rsp+arg_0], rbx
0x140034181  push    rdi
0x140034182  sub     rsp, 60h
0x140034186  mov     rax, cs:__security_cookie
0x14003418d  xor     rax, rsp
0x140034190  mov     [rsp+68h+var_18], rax
0x140034195  mov     rcx, cs:WPP_GLOBAL_Control
0x14003419c  lea     rdi, WPP_GLOBAL_Control
0x1400341a3  cmp     rcx, rdi
0x1400341a6  jz      short loc_1400341C9
0x1400341a8  test    byte ptr [rcx+1Ch], 4
0x1400341ac  jz      short loc_1400341C9
0x1400341ae  cmp     byte ptr [rcx+19h], 5
0x1400341b2  jb      short loc_1400341C9
0x1400341b4  mov     rcx, [rcx+10h]
0x1400341b8  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400341bf  mov     edx, 87h
0x1400341c4  call    WPP_SF_
0x1400341c9  mov     ebx, 1
0x1400341ce  xor     r8d, r8d; CompletionKey
0x1400341d1  mov     r9d, ebx; NumberOfConcurrentThreads
0x1400341d4  xor     edx, edx; ExistingCompletionPort
0x1400341d6  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x1400341da  call    cs:__imp_CreateIoCompletionPort
0x1400341e1  nop     dword ptr [rax+rax+00h]
0x1400341e6  mov     cs:?g_StatusCompletionPortHandle@@3PEAXEA, rax; void * g_StatusCompletionPortHandle
0x1400341ed  test    rax, rax
0x1400341f0  jnz     loc_14003428D
0x1400341f6  call    cs:__imp_GetLastError
0x1400341fd  nop     dword ptr [rax+rax+00h]
0x140034202  xor     ecx, ecx
0x140034204  lea     r8, aLd; "%ld"
0x14003420b  lea     edx, [rbx+0Bh]; unsigned __int64
0x14003420e  mov     [rsp+68h+var_38], eax
0x140034212  mov     [rsp+68h+var_34], cx
0x140034217  mov     r9d, eax
0x14003421a  lea     rcx, [rsp+68h+var_34]; unsigned __int16 *
0x14003421f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140034224  xor     ecx, ecx
0x140034226  lea     rdx, [rsp+68h+var_34]
0x14003422b  test    eax, eax
0x14003422d  mov     r9d, 0C0007D2Ch
0x140034233  mov     r8d, ebx
0x140034236  cmovs   rdx, rcx
0x14003423a  mov     ecx, ebx
0x14003423c  mov     [rsp+68h+var_48], rdx
0x140034241  mov     edx, ebx
0x140034243  call    FaxLog
0x140034248  mov     rax, cs:WPP_GLOBAL_Control
0x14003424f  cmp     rax, rdi
0x140034252  jz      short loc_14003428B
0x140034254  test    byte ptr [rax+1Ch], 4
0x140034258  jz      short loc_14003428B
0x14003425a  cmp     byte ptr [rax+19h], 2
0x14003425e  jb      short loc_14003428B
0x140034260  call    cs:__imp_GetLastError
0x140034267  nop     dword ptr [rax+rax+00h]
0x14003426c  mov     rcx, cs:WPP_GLOBAL_Control
0x140034273  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003427a  mov     edx, 88h
0x14003427f  mov     r9d, eax
0x140034282  mov     rcx, [rcx+10h]
0x140034286  call    WPP_SF_d
0x14003428b  xor     ebx, ebx
0x14003428d  mov     eax, ebx
0x14003428f  mov     rcx, [rsp+68h+var_18]
0x140034294  xor     rcx, rsp; StackCookie
0x140034297  call    __security_check_cookie
0x14003429c  mov     rbx, [rsp+68h+arg_0]
0x1400342a1  add     rsp, 60h
0x1400342a5  pop     rdi
0x1400342a6  retn
```
