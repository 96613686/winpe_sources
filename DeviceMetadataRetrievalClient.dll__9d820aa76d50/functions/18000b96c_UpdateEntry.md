# UpdateEntry

- ea: `0x18000b96c`
- end: `0x18000bbb0`
- name: `UpdateEntry`
- size: `580`
- prototype: `__int64 __fastcall(__int64, struct UNNAMED_STRUCT_MAP_STRING *, const unsigned __int16 *, int, wchar_t *String2, wchar_t *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800066b0`

## callees

- `0x180002bd8`
- `0x180004dc4`
- `0x180007f3c`
- `0x18000b96c`
- `0x18000c014`
- `0x1800135cc`
- `0x180013700`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ba71`
- `msvcrt!_wcsicmp` at `0x18000bad3`
- `msvcrt!_wcsicmp` at `0x18000ba71`
- `msvcrt!_wcsicmp` at `0x18000bad3`
- `KERNEL32!GetProcessHeap` at `0x18000bb55`
- `KERNEL32!GetProcessHeap` at `0x18000bb6e`
- `KERNEL32!GetProcessHeap` at `0x18000bb55`
- `KERNEL32!GetProcessHeap` at `0x18000bb6e`
- `KERNEL32!HeapFree` at `0x18000bb63`
- `KERNEL32!HeapFree` at `0x18000bb7c`
- `KERNEL32!HeapFree` at `0x18000bb63`
- `KERNEL32!HeapFree` at `0x18000bb7c`
- `KERNEL32!AcquireSRWLockShared` at `0x18000ba13`
- `KERNEL32!AcquireSRWLockShared` at `0x18000ba13`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000bb4a`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000bb4a`
- `DEVRTL!NdxTableObjectFromName` at `0x18000ba38`
- `DEVRTL!NdxTableObjectFromName` at `0x18000ba38`

## pseudocode

```c
__int64 __fastcall UpdateEntry(
        __int64 a1,
        struct UNNAMED_STRUCT_MAP_STRING *a2,
        const unsigned __int16 *a3,
        int a4,
        wchar_t *String2,
        wchar_t *a6,
        _DWORD *a7)
{
  RTL_SRWLOCK *v9; // r13
  wchar_t *v10; // rbp
  wchar_t *v11; // rsi
  int v12; // eax
  unsigned int v13; // ebx
  const wchar_t *v14; // rax
  void **v15; // r8
  const wchar_t *ObjectString; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v18; // rax
  _OWORD v22[2]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v23; // [rsp+60h] [rbp-48h]

  v23 = 0;
  memset(v22, 0, sizeof(v22));
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( a4 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a1 || *(_DWORD *)a1 != 1229866053 || !a7 )
    return 87;
  v9 = (RTL_SRWLOCK *)(a1 + 32);
  v10 = 0;
  v11 = 0;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 32));
  *a7 = 0;
  if ( a4 != 1 )
  {
    v13 = 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids);
    goto LABEL_30;
  }
  v12 = NdxTableObjectFromName(*(_QWORD *)(a1 + 40), 0, a3, v22);
  v13 = 0;
  if ( v12 )
  {
    if ( String2
      && (v14 = MemGetObjectString((struct NDX_OBJREF *)v22, 2), (v10 = (wchar_t *)v14) != 0)
      && _wcsicmp(v14, String2) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          (unsigned int)&WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
          (_DWORD)v10,
          (__int64)String2);
    }
    else
    {
      ObjectString = MemGetObjectString((struct NDX_OBJREF *)v22, 0);
      v11 = (wchar_t *)ObjectString;
      if ( !ObjectString || !_wcsicmp(ObjectString, a6) )
      {
        *a7 = 0;
        goto LABEL_26;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          40,
          (unsigned int)&WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
          (_DWORD)v11,
          (__int64)a6);
    }
    *a7 = 1;
LABEL_26:
    MapStringDeleteV(a2, a3, v15);
    goto LABEL_30;
  }
  *a7 = 1;
LABEL_30:
  ReleaseSRWLockShared(v9);
  if ( v10 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  if ( v11 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v11);
  }
  return v13;
}

```

## disassembly

```asm
0x18000b96c  mov     [rsp+arg_18], rbx
0x18000b971  push    rbp
0x18000b972  push    rsi
0x18000b973  push    rdi
0x18000b974  push    r12
0x18000b976  push    r13
0x18000b978  push    r14
0x18000b97a  push    r15
0x18000b97c  sub     rsp, 70h
0x18000b980  mov     rax, cs:__security_cookie
0x18000b987  xor     rax, rsp
0x18000b98a  mov     [rsp+0A8h+var_40], rax
0x18000b98f  mov     r15, [rsp+0A8h+String2]
0x18000b997  xorps   xmm0, xmm0
0x18000b99a  mov     r12, [rsp+0A8h+arg_28]
0x18000b9a2  mov     rbx, rcx
0x18000b9a5  mov     rdi, [rsp+0A8h+arg_30]
0x18000b9ad  xor     ecx, ecx
0x18000b9af  mov     [rsp+0A8h+var_78], r8
0x18000b9b4  mov     r14d, r9d
0x18000b9b7  mov     [rsp+0A8h+var_70], rdx
0x18000b9bc  mov     [rsp+0A8h+var_48], rcx
0x18000b9c1  movups  [rsp+0A8h+var_68], xmm0
0x18000b9c6  movups  [rsp+0A8h+var_58], xmm0
0x18000b9cb  test    rdx, rdx
0x18000b9ce  jnz     short loc_18000B9D5
0x18000b9d0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b9d5  cmp     r14d, 1
0x18000b9d9  jz      short loc_18000B9E0
0x18000b9db  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b9e0  test    r12, r12
0x18000b9e3  jnz     short loc_18000B9EA
0x18000b9e5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b9ea  test    rbx, rbx
0x18000b9ed  jz      loc_18000BB86
0x18000b9f3  cmp     dword ptr [rbx], 494E4445h
0x18000b9f9  jnz     loc_18000BB86
0x18000b9ff  test    rdi, rdi
0x18000ba02  jz      loc_18000BB86
0x18000ba08  lea     r13, [rbx+20h]
0x18000ba0c  xor     ebp, ebp
0x18000ba0e  mov     rcx, r13; SRWLock
0x18000ba11  xor     esi, esi
0x18000ba13  call    cs:__imp_AcquireSRWLockShared
0x18000ba19  mov     [rdi], esi
0x18000ba1b  cmp     r14d, 1
0x18000ba1f  jnz     loc_18000BB16
0x18000ba25  mov     r14, [rsp+0A8h+var_78]
0x18000ba2a  lea     r9, [rsp+0A8h+var_68]
0x18000ba2f  mov     rcx, [rbx+28h]
0x18000ba33  mov     r8, r14
0x18000ba36  xor     edx, edx
0x18000ba38  call    cs:__imp_NdxTableObjectFromName
0x18000ba3e  xor     ebx, ebx
0x18000ba40  test    eax, eax
0x18000ba42  jnz     short loc_18000BA4F
0x18000ba44  mov     dword ptr [rdi], 1
0x18000ba4a  jmp     loc_18000BB47
0x18000ba4f  test    r15, r15
0x18000ba52  jz      short loc_18000BAB9
0x18000ba54  mov     edx, 2; int
0x18000ba59  lea     rcx, [rsp+0A8h+var_68]; struct NDX_OBJREF *
0x18000ba5e  call    ?MemGetObjectString@@YAPEAGPEAUNDX_OBJREF@@J@Z; MemGetObjectString(NDX_OBJREF *,long)
0x18000ba63  mov     rbp, rax
0x18000ba66  test    rax, rax
0x18000ba69  jz      short loc_18000BAB9
0x18000ba6b  mov     rdx, r15; String2
0x18000ba6e  mov     rcx, rax; String1
0x18000ba71  call    cs:__imp__wcsicmp
0x18000ba77  test    eax, eax
0x18000ba79  jz      short loc_18000BAB9
0x18000ba7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba82  lea     rdx, WPP_GLOBAL_Control
0x18000ba89  cmp     rcx, rdx
0x18000ba8c  jz      short loc_18000BAB1
0x18000ba8e  test    byte ptr [rcx+1Ch], 2
0x18000ba92  jz      short loc_18000BAB1
0x18000ba94  mov     edx, 27h ; '''
0x18000ba99  mov     [rsp+0A8h+var_88], r15
0x18000ba9e  mov     r9, rbp
0x18000baa1  mov     rcx, [rcx+10h]
0x18000baa5  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000baac  call    WPP_SF_SS
0x18000bab1  mov     dword ptr [rdi], 1
0x18000bab7  jmp     short loc_18000BB07
0x18000bab9  xor     edx, edx; int
0x18000babb  lea     rcx, [rsp+0A8h+var_68]; struct NDX_OBJREF *
0x18000bac0  call    ?MemGetObjectString@@YAPEAGPEAUNDX_OBJREF@@J@Z; MemGetObjectString(NDX_OBJREF *,long)
0x18000bac5  mov     rsi, rax
0x18000bac8  test    rax, rax
0x18000bacb  jz      short loc_18000BB05
0x18000bacd  mov     rdx, r12; String2
0x18000bad0  mov     rcx, rax; String1
0x18000bad3  call    cs:__imp__wcsicmp
0x18000bad9  test    eax, eax
0x18000badb  jz      short loc_18000BB05
0x18000badd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bae4  lea     rdx, WPP_GLOBAL_Control
0x18000baeb  cmp     rcx, rdx
0x18000baee  jz      short loc_18000BAB1
0x18000baf0  test    byte ptr [rcx+1Ch], 2
0x18000baf4  jz      short loc_18000BAB1
0x18000baf6  mov     edx, 28h ; '('
0x18000bafb  mov     [rsp+0A8h+var_88], r12
0x18000bb00  mov     r9, rsi
0x18000bb03  jmp     short loc_18000BAA1
0x18000bb05  mov     [rdi], ebx
0x18000bb07  mov     rcx, [rsp+0A8h+var_70]; struct UNNAMED_STRUCT_MAP_STRING *
0x18000bb0c  mov     rdx, r14; unsigned __int16 *
0x18000bb0f  call    ?MapStringDeleteV@@YAHPEAUUNNAMED_STRUCT_MAP_STRING@@PEBGPEAPEAX@Z; MapStringDeleteV(UNNAMED_STRUCT_MAP_STRING *,ushort const *,void * *)
0x18000bb14  jmp     short loc_18000BB47
0x18000bb16  mov     ebx, 57h ; 'W'
0x18000bb1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb22  lea     rdx, WPP_GLOBAL_Control
0x18000bb29  cmp     rcx, rdx
0x18000bb2c  jz      short loc_18000BB47
0x18000bb2e  test    byte ptr [rcx+1Ch], 1
0x18000bb32  jz      short loc_18000BB47
0x18000bb34  mov     rcx, [rcx+10h]
0x18000bb38  lea     edx, [rbx-31h]
0x18000bb3b  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000bb42  call    WPP_SF_
0x18000bb47  mov     rcx, r13; SRWLock
0x18000bb4a  call    cs:__imp_ReleaseSRWLockShared
0x18000bb50  test    rbp, rbp
0x18000bb53  jz      short loc_18000BB69
0x18000bb55  call    cs:__imp_GetProcessHeap
0x18000bb5b  mov     r8, rbp; lpMem
0x18000bb5e  xor     edx, edx; dwFlags
0x18000bb60  mov     rcx, rax; hHeap
0x18000bb63  call    cs:__imp_HeapFree
0x18000bb69  test    rsi, rsi
0x18000bb6c  jz      short loc_18000BB82
0x18000bb6e  call    cs:__imp_GetProcessHeap
0x18000bb74  mov     r8, rsi; lpMem
0x18000bb77  xor     edx, edx; dwFlags
0x18000bb79  mov     rcx, rax; hHeap
0x18000bb7c  call    cs:__imp_HeapFree
0x18000bb82  mov     eax, ebx
0x18000bb84  jmp     short loc_18000BB8B
0x18000bb86  mov     eax, 57h ; 'W'
0x18000bb8b  mov     rcx, [rsp+0A8h+var_40]
0x18000bb90  xor     rcx, rsp; StackCookie
0x18000bb93  call    __security_check_cookie
0x18000bb98  mov     rbx, [rsp+0A8h+arg_18]
0x18000bba0  add     rsp, 70h
0x18000bba4  pop     r15
0x18000bba6  pop     r14
0x18000bba8  pop     r13
0x18000bbaa  pop     r12
0x18000bbac  pop     rdi
0x18000bbad  pop     rsi
0x18000bbae  pop     rbp
0x18000bbaf  retn
```
