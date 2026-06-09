# CFspFileSystemOperations::GetSecurity(void *,ulong,void * *)

- ea: `0x1801127bc`
- end: `0x180112957`
- name: `?GetSecurity@CFspFileSystemOperations@@SAJPEAXKPEAPEAX@Z`
- size: `411`
- prototype: `__int64 __fastcall(HANDLE Handle, unsigned int, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18010fd2c`

## callees

- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x180090c60`
- `0x1800984c8`
- `0x1801127bc`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x18011289f`
- `ntdll!NtQuerySecurityObject` at `0x180112903`
- `ntdll!NtQuerySecurityObject` at `0x18011289f`
- `ntdll!NtQuerySecurityObject` at `0x180112903`

## string_xrefs

- `0x180112832`: `CFspFileSystemOperations::GetSecurity`

## pseudocode

```c
__int64 __fastcall CFspFileSystemOperations::GetSecurity(HANDLE Handle, ULONG a2, void **a3)
{
  _DWORD *v5; // rax
  char v6; // cl
  __int16 v7; // ax
  int v8; // ebx
  bool v9; // zf
  int v10; // eax
  PSECURITY_DESCRIPTOR v11; // rdi
  bool v12; // sf
  __int16 v13; // ax
  unsigned int v14; // eax
  int v16; // [rsp+30h] [rbp-20h] BYREF
  int v17; // [rsp+34h] [rbp-1Ch]
  char v18; // [rsp+38h] [rbp-18h]
  const char *v19; // [rsp+40h] [rbp-10h]
  __int64 v20; // [rsp+48h] [rbp-8h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+20h] BYREF
  ULONG Length; // [rsp+78h] [rbp+28h] BYREF

  Length = a2;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, WPP_ce5b6c69d76e344a5abed05d444096ed_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( (v5[17] & 0x100) != 0 && *((_BYTE *)v5 + 65) >= 6u )
  {
    v6 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v6 = 0;
LABEL_9:
  v17 = 800;
  v19 = "CFspFileSystemOperations::GetSecurity";
  v18 = v6;
  v20 = 0;
  SecurityDescriptor = 0;
  Length = 0;
  if ( a3 )
    *a3 = 0;
  v7 = 807;
  if ( !Handle )
  {
    v8 = -2147024809;
LABEL_13:
    v16 = v8;
    HIWORD(v17) = v7;
    goto LABEL_22;
  }
  LOWORD(v17) = 807;
  v16 = 0;
  v9 = NtQuerySecurityObject(Handle, 4u, 0, 0, &Length) == -1073741789;
  v7 = 815;
  if ( !v9 )
  {
    v8 = -2147418113;
    goto LABEL_13;
  }
  LOWORD(v17) = 815;
  v10 = EcsAlloc(Length, &SecurityDescriptor);
  v11 = SecurityDescriptor;
  v8 = v10;
  v16 = v10;
  v12 = v10 < 0;
  v13 = 819;
  if ( v12
    || (LOWORD(v17) = 819,
        v14 = NtQuerySecurityObject(Handle, 4u, SecurityDescriptor, Length, &Length),
        v8 = HRESULTFromNTSTATUS(v14),
        v16 = v8,
        v13 = 825,
        v8 < 0) )
  {
    HIWORD(v17) = v13;
  }
  else
  {
    *a3 = v11;
    v11 = 0;
    LOWORD(v17) = 825;
  }
  if ( v11 )
  {
    EcsFree(v11);
    v8 = v16;
  }
LABEL_22:
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1801127bc  mov     [rsp-18h+arg_10], rbx
0x1801127c1  mov     [rsp-18h+arg_18], rsi
0x1801127c6  mov     [rsp-18h+Length], edx
0x1801127ca  push    rbp
0x1801127cb  push    rdi
0x1801127cc  push    r14
0x1801127ce  mov     rbp, rsp
0x1801127d1  sub     rsp, 50h
0x1801127d5  mov     rsi, r8
0x1801127d8  mov     r14, rcx
0x1801127db  mov     rax, cs:WPP_GLOBAL_Control
0x1801127e2  lea     rcx, WPP_GLOBAL_Control
0x1801127e9  mov     ebx, 100h
0x1801127ee  cmp     rax, rcx
0x1801127f1  jz      short loc_18011281A
0x1801127f3  test    [rax+44h], ebx
0x1801127f6  jz      short loc_180112829
0x1801127f8  cmp     byte ptr [rax+41h], 6
0x1801127fc  jb      short loc_18011281A
0x1801127fe  mov     rcx, [rax+38h]
0x180112802  lea     r8, WPP_ce5b6c69d76e344a5abed05d444096ed_Traceguids
0x180112809  mov     edx, 18h
0x18011280e  call    WPP_SF_
0x180112813  mov     rax, cs:WPP_GLOBAL_Control
0x18011281a  test    [rax+44h], ebx
0x18011281d  jz      short loc_180112829
0x18011281f  cmp     byte ptr [rax+41h], 6
0x180112823  jb      short loc_180112829
0x180112825  mov     cl, 1
0x180112827  jmp     short loc_18011282B
0x180112829  xor     cl, cl
0x18011282b  mov     [rbp+var_1C], 320h
0x180112832  lea     rax, aCfspfilesystem_0; "CFspFileSystemOperations::GetSecurity"
0x180112839  mov     [rbp+var_10], rax
0x18011283d  mov     [rbp+var_18], cl
0x180112840  mov     [rbp+var_8], 0
0x180112848  mov     [rbp+SecurityDescriptor], 0
0x180112850  mov     [rbp+Length], 0
0x180112857  test    rsi, rsi
0x18011285a  jz      short loc_180112863
0x18011285c  mov     qword ptr [rsi], 0
0x180112863  mov     eax, 327h
0x180112868  test    r14, r14
0x18011286b  jnz     short loc_18011287E
0x18011286d  mov     ebx, 80070057h
0x180112872  mov     [rbp+var_20], ebx
0x180112875  mov     word ptr [rbp+var_1C+2], ax
0x180112879  jmp     loc_180112937
0x18011287e  xor     r9d, r9d; Length
0x180112881  mov     word ptr [rbp+var_1C], ax
0x180112885  lea     rax, [rbp+Length]
0x180112889  mov     [rbp+var_20], 0
0x180112890  xor     r8d, r8d; SecurityDescriptor
0x180112893  mov     [rsp+50h+LengthNeeded], rax; LengthNeeded
0x180112898  mov     rcx, r14; Handle
0x18011289b  lea     edx, [r9+4]; SecurityInformation
0x18011289f  call    cs:__imp_NtQuerySecurityObject
0x1801128a5  cmp     eax, 0C0000023h
0x1801128aa  mov     eax, 32Fh
0x1801128af  jz      short loc_1801128B8
0x1801128b1  mov     ebx, 8000FFFFh
0x1801128b6  jmp     short loc_180112872
0x1801128b8  mov     ecx, [rbp+Length]; unsigned __int64
0x1801128bb  lea     rdx, [rbp+SecurityDescriptor]; void **
0x1801128bf  mov     [rbp+var_20], 0
0x1801128c6  mov     word ptr [rbp+var_1C], ax
0x1801128ca  call    ?EcsAlloc@@YAJ_KPEAPEAX@Z; EcsAlloc(unsigned __int64,void * *)
0x1801128cf  mov     rdi, [rbp+SecurityDescriptor]
0x1801128d3  mov     ebx, eax
0x1801128d5  mov     [rbp+var_20], eax
0x1801128d8  test    eax, eax
0x1801128da  mov     eax, 333h
0x1801128df  jns     short loc_1801128E7
0x1801128e1  mov     word ptr [rbp+var_1C+2], ax
0x1801128e5  jmp     short loc_180112927
0x1801128e7  mov     r9d, [rbp+Length]; Length
0x1801128eb  mov     r8, rdi; SecurityDescriptor
0x1801128ee  mov     word ptr [rbp+var_1C], ax
0x1801128f2  mov     edx, 4; SecurityInformation
0x1801128f7  lea     rax, [rbp+Length]
0x1801128fb  mov     rcx, r14; Handle
0x1801128fe  mov     [rsp+50h+LengthNeeded], rax; LengthNeeded
0x180112903  call    cs:__imp_NtQuerySecurityObject
0x180112909  mov     ecx, eax
0x18011290b  call    HRESULTFromNTSTATUS
0x180112910  mov     ebx, eax
0x180112912  mov     [rbp+var_20], eax
0x180112915  test    eax, eax
0x180112917  mov     eax, 339h
0x18011291c  js      short loc_1801128E1
0x18011291e  mov     [rsi], rdi
0x180112921  xor     edi, edi
0x180112923  mov     word ptr [rbp+var_1C], ax
0x180112927  test    rdi, rdi
0x18011292a  jz      short loc_180112937
0x18011292c  mov     rcx, rdi; void *
0x18011292f  call    ?EcsFree@@YAJPEAX@Z; EcsFree(void *)
0x180112934  mov     ebx, [rbp+var_20]
0x180112937  lea     rcx, [rbp+var_20]; this
0x18011293b  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180112940  lea     r11, [rsp+50h+var_s0]
0x180112945  mov     eax, ebx
0x180112947  mov     rbx, [r11+30h]
0x18011294b  mov     rsi, [r11+38h]
0x18011294f  mov     rsp, r11
0x180112952  pop     r14
0x180112954  pop     rdi
0x180112955  pop     rbp
0x180112956  retn
```
