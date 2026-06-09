# CManagedAppProcessor::GetAppsFromDirectory(void)

- ea: `0x18000f634`
- end: `0x18000f8b6`
- name: `?GetAppsFromDirectory@CManagedAppProcessor@@AEAAJXZ`
- size: `642`
- prototype: `signed int __fastcall(CManagedAppProcessor *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001069c`
- `0x180011ac0`

## callees

- `0x1800016d0`
- `0x18000f024`
- `0x18000f634`
- `0x18000fde0`
- `0x180012d70`
- `0x18001309c`
- `0x18001b1a0`
- `0x18001bae0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6aa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f88a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000f88a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000f680`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000f680`
- `ADVAPI32!GetUserNameW` at `0x18000f71a`
- `ADVAPI32!GetUserNameW` at `0x18000f71a`
- `KERNEL32!GetComputerNameW` at `0x18000f763`
- `KERNEL32!GetComputerNameW` at `0x18000f763`

## pseudocode

```c
signed int __fastcall CManagedAppProcessor::GetAppsFromDirectory(CManagedAppProcessor *this)
{
  bool v1; // zf
  DWORD LastError; // eax
  signed int result; // eax
  int v5; // eax
  unsigned int v6; // r14d
  int (*v7)(HINSTANCE, unsigned int, unsigned __int16 *, int); // rdi
  DWORD v8; // ebx
  HINSTANCE HandleForCallingDll; // rax
  int (*v10)(HINSTANCE, unsigned int, unsigned __int16 *, int); // rdi
  DWORD v11; // ebx
  HINSTANCE v12; // rax
  int ClassAccessFromPath; // ebx
  const unsigned __int16 *v14; // rdx
  DWORD pcbBuffer[2]; // [rsp+40h] [rbp-19h] BYREF
  struct IEnumPackage *v16; // [rsp+48h] [rbp-11h] BYREF
  WCHAR Buffer[32]; // [rsp+50h] [rbp-9h] BYREF

  v1 = *((_DWORD *)this + 99) == 1;
  v16 = 0;
  if ( v1 || !*((_DWORD *)this + 74) || ImpersonateLoggedOnUser(*((HANDLE *)this + 33)) )
    goto LABEL_9;
  if ( *(_DWORD *)&gDebugLevel )
  {
    LastError = GetLastError();
    _DebugMsg(2, 0xBC4u, LastError);
  }
  result = GetLastError();
  if ( !result )
  {
LABEL_9:
    v5 = *((_DWORD *)this + 77);
    if ( *((_DWORD *)this + 98) )
      v6 = (v5 != 0) + 5;
    else
      v6 = (v5 != 0) + 3;
    if ( (gDebugLevel & 2) != 0 )
    {
      pcbBuffer[0] = 32;
      Buffer[0] = 0;
      if ( *((_DWORD *)this + 74) )
      {
        if ( !GetUserNameW(Buffer, pcbBuffer) && (unsigned int)LoadLoadString() )
        {
          v7 = pfnLoadStringW;
          v8 = pcbBuffer[0];
          HandleForCallingDll = AppmgmtGetHandleForCallingDll();
          ((void (__fastcall *)(HINSTANCE, __int64, WCHAR *, _QWORD))v7)(HandleForCallingDll, 3015, Buffer, v8);
        }
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xBC8u, Buffer, v6);
      }
      else
      {
        if ( !GetComputerNameW(Buffer, pcbBuffer) && (unsigned int)LoadLoadString() )
        {
          v10 = pfnLoadStringW;
          v11 = pcbBuffer[0];
          v12 = AppmgmtGetHandleForCallingDll();
          ((void (__fastcall *)(HINSTANCE, __int64, WCHAR *, _QWORD))v10)(v12, 3015, Buffer, v11);
        }
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xBE9u, Buffer, v6);
      }
    }
    if ( *((_DWORD *)this + 99) == 1 )
    {
      v14 = (const unsigned __int16 *)*((_QWORD *)this + 30);
      *(_QWORD *)pcbBuffer = 0;
      ClassAccessFromPath = CManagedAppProcessor::GetClassAccessFromPath(this, v14, (struct IClassAccess **)pcbBuffer);
      if ( ClassAccessFromPath >= 0 )
      {
        ClassAccessFromPath = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int, struct IEnumPackage **))(**(_QWORD **)pcbBuffer + 32LL))(
                                *(_QWORD *)pcbBuffer,
                                0,
                                0,
                                0,
                                v6,
                                &v16);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbBuffer + 16LL))(*(_QWORD *)pcbBuffer);
      }
    }
    else
    {
      ClassAccessFromPath = CsEnumApps(0, 0, 0, v6, (__int64)&v16);
    }
    if ( ClassAccessFromPath )
    {
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(2, 0xBC9u, (unsigned int)ClassAccessFromPath);
    }
    else
    {
      ClassAccessFromPath = CManagedAppProcessor::EnumerateApps((LPCWSTR **)this, v16);
      (*(void (__fastcall **)(struct IEnumPackage *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    if ( *((_DWORD *)this + 99) != 1 && *((_DWORD *)this + 74) )
      RevertToSelf();
    return ClassAccessFromPath;
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000f634  mov     [rsp-8+arg_8], rbx
0x18000f639  mov     [rsp-8+arg_10], rsi
0x18000f63e  push    rbp
0x18000f63f  push    rdi
0x18000f640  push    r14
0x18000f642  lea     rbp, [rsp-47h]
0x18000f647  sub     rsp, 0A0h
0x18000f64e  mov     rax, cs:__security_cookie
0x18000f655  xor     rax, rsp
0x18000f658  mov     [rbp+57h+var_20], rax
0x18000f65c  cmp     dword ptr [rcx+18Ch], 1
0x18000f663  mov     rsi, rcx
0x18000f666  mov     [rbp+57h+var_68], 0
0x18000f66e  jz      short loc_18000F6C7
0x18000f670  cmp     dword ptr [rcx+128h], 0
0x18000f677  jz      short loc_18000F6C7
0x18000f679  mov     rcx, [rcx+108h]; hToken
0x18000f680  call    cs:__imp_ImpersonateLoggedOnUser
0x18000f686  test    eax, eax
0x18000f688  jnz     short loc_18000F6C7
0x18000f68a  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x18000f690  jz      short loc_18000F6AA
0x18000f692  call    cs:__imp_GetLastError
0x18000f698  mov     edx, 0BC4h; unsigned int
0x18000f69d  mov     ecx, 2; unsigned int
0x18000f6a2  mov     r8d, eax
0x18000f6a5  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000f6aa  call    cs:__imp_GetLastError
0x18000f6b0  test    eax, eax
0x18000f6b2  jz      short loc_18000F6C7
0x18000f6b4  jle     loc_18000F892
0x18000f6ba  movzx   eax, ax
0x18000f6bd  or      eax, 80070000h
0x18000f6c2  jmp     loc_18000F892
0x18000f6c7  cmp     dword ptr [rsi+188h], 0
0x18000f6ce  mov     eax, [rsi+134h]
0x18000f6d4  jz      short loc_18000F6E4
0x18000f6d6  neg     eax
0x18000f6d8  sbb     r14d, r14d
0x18000f6db  neg     r14d
0x18000f6de  add     r14d, 5
0x18000f6e2  jmp     short loc_18000F6F0
0x18000f6e4  neg     eax
0x18000f6e6  sbb     r14d, r14d
0x18000f6e9  neg     r14d
0x18000f6ec  add     r14d, 3
0x18000f6f0  test    byte ptr cs:?gDebugLevel@@3KA, 2; ulong gDebugLevel
0x18000f6f7  jz      loc_18000F7BB
0x18000f6fd  xor     eax, eax
0x18000f6ff  mov     [rbp+57h+pcbBuffer], 20h ; ' '
0x18000f706  lea     rdx, [rbp+57h+pcbBuffer]; nSize
0x18000f70a  mov     [rbp+57h+Buffer], ax
0x18000f70e  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x18000f712  cmp     [rsi+128h], eax
0x18000f718  jz      short loc_18000F763
0x18000f71a  call    cs:__imp_GetUserNameW
0x18000f720  test    eax, eax
0x18000f722  jnz     short loc_18000F753
0x18000f724  call    ?LoadLoadString@@YAHXZ; LoadLoadString(void)
0x18000f729  test    eax, eax
0x18000f72b  jz      short loc_18000F753
0x18000f72d  mov     rdi, cs:?pfnLoadStringW@@3P6AHPEAUHINSTANCE__@@IPEAGH@ZEA; int (*pfnLoadStringW)(HINSTANCE__ *,uint,ushort *,int)
0x18000f734  mov     ebx, [rbp+57h+pcbBuffer]
0x18000f737  call    ?AppmgmtGetHandleForCallingDll@@YAPEAUHINSTANCE__@@XZ; AppmgmtGetHandleForCallingDll(void)
0x18000f73c  mov     rcx, rax
0x18000f73f  lea     r8, [rbp+57h+Buffer]
0x18000f743  mov     rax, rdi
0x18000f746  mov     r9d, ebx
0x18000f749  mov     edx, 0BC7h
0x18000f74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f753  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000f75a  jz      short loc_18000F7BB
0x18000f75c  mov     edx, 0BC8h
0x18000f761  jmp     short loc_18000F7AA
0x18000f763  call    cs:__imp_GetComputerNameW
0x18000f769  test    eax, eax
0x18000f76b  jnz     short loc_18000F79C
0x18000f76d  call    ?LoadLoadString@@YAHXZ; LoadLoadString(void)
0x18000f772  test    eax, eax
0x18000f774  jz      short loc_18000F79C
0x18000f776  mov     rdi, cs:?pfnLoadStringW@@3P6AHPEAUHINSTANCE__@@IPEAGH@ZEA; int (*pfnLoadStringW)(HINSTANCE__ *,uint,ushort *,int)
0x18000f77d  mov     ebx, [rbp+57h+pcbBuffer]
0x18000f780  call    ?AppmgmtGetHandleForCallingDll@@YAPEAUHINSTANCE__@@XZ; AppmgmtGetHandleForCallingDll(void)
0x18000f785  mov     rcx, rax
0x18000f788  lea     r8, [rbp+57h+Buffer]
0x18000f78c  mov     rax, rdi
0x18000f78f  mov     r9d, ebx
0x18000f792  mov     edx, 0BC7h
0x18000f797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f79c  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000f7a3  jz      short loc_18000F7BB
0x18000f7a5  mov     edx, 0BE9h; unsigned int
0x18000f7aa  mov     r9d, r14d
0x18000f7ad  lea     r8, [rbp+57h+Buffer]
0x18000f7b1  mov     ecx, 4; unsigned int
0x18000f7b6  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000f7bb  cmp     dword ptr [rsi+18Ch], 1
0x18000f7c2  jz      short loc_18000F7E0
0x18000f7c4  lea     rax, [rbp+57h+var_68]
0x18000f7c8  mov     r9d, r14d
0x18000f7cb  xor     r8d, r8d
0x18000f7ce  mov     [rsp+0B0h+var_90], rax
0x18000f7d3  xor     edx, edx
0x18000f7d5  xor     ecx, ecx
0x18000f7d7  call    CsEnumApps
0x18000f7dc  mov     ebx, eax
0x18000f7de  jmp     short loc_18000F839
0x18000f7e0  mov     rdx, [rsi+0F0h]; unsigned __int16 *
0x18000f7e7  lea     r8, [rbp+57h+pcbBuffer]; struct IClassAccess **
0x18000f7eb  mov     rcx, rsi; this
0x18000f7ee  mov     qword ptr [rbp+57h+pcbBuffer], 0
0x18000f7f6  call    ?GetClassAccessFromPath@CManagedAppProcessor@@AEAAJPEBGPEAPEAUIClassAccess@@@Z; CManagedAppProcessor::GetClassAccessFromPath(ushort const *,IClassAccess * *)
0x18000f7fb  mov     ebx, eax
0x18000f7fd  test    eax, eax
0x18000f7ff  js      short loc_18000F839
0x18000f801  mov     rcx, qword ptr [rbp+57h+pcbBuffer]
0x18000f805  lea     rdx, [rbp+57h+var_68]
0x18000f809  mov     [rsp+0B0h+var_88], rdx
0x18000f80e  xor     r9d, r9d
0x18000f811  xor     r8d, r8d
0x18000f814  mov     dword ptr [rsp+0B0h+var_90], r14d
0x18000f819  xor     edx, edx
0x18000f81b  mov     rax, [rcx]
0x18000f81e  mov     rax, [rax+20h]
0x18000f822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f827  mov     rcx, qword ptr [rbp+57h+pcbBuffer]
0x18000f82b  mov     ebx, eax
0x18000f82d  mov     rax, [rcx]
0x18000f830  mov     rax, [rax+10h]
0x18000f834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f839  test    ebx, ebx
0x18000f83b  jnz     short loc_18000F85D
0x18000f83d  mov     rdx, [rbp+57h+var_68]; struct IEnumPackage *
0x18000f841  mov     rcx, rsi; this
0x18000f844  call    ?EnumerateApps@CManagedAppProcessor@@AEAAJPEAUIEnumPackage@@@Z; CManagedAppProcessor::EnumerateApps(IEnumPackage *)
0x18000f849  mov     rcx, [rbp+57h+var_68]
0x18000f84d  mov     ebx, eax
0x18000f84f  mov     rax, [rcx]
0x18000f852  mov     rax, [rax+10h]
0x18000f856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f85b  jmp     short loc_18000F878
0x18000f85d  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000f864  jz      short loc_18000F878
0x18000f866  mov     r8d, ebx
0x18000f869  mov     edx, 0BC9h; unsigned int
0x18000f86e  mov     ecx, 2; unsigned int
0x18000f873  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000f878  cmp     dword ptr [rsi+18Ch], 1
0x18000f87f  jz      short loc_18000F890
0x18000f881  cmp     dword ptr [rsi+128h], 0
0x18000f888  jz      short loc_18000F890
0x18000f88a  call    cs:__imp_RevertToSelf
0x18000f890  mov     eax, ebx
0x18000f892  mov     rcx, [rbp+57h+var_20]
0x18000f896  xor     rcx, rsp; StackCookie
0x18000f899  call    __security_check_cookie
0x18000f89e  lea     r11, [rsp+0B0h+var_10]
0x18000f8a6  mov     rbx, [r11+28h]
0x18000f8aa  mov     rsi, [r11+30h]
0x18000f8ae  mov     rsp, r11
0x18000f8b1  pop     r14
0x18000f8b3  pop     rdi
0x18000f8b4  pop     rbp
0x18000f8b5  retn
```
