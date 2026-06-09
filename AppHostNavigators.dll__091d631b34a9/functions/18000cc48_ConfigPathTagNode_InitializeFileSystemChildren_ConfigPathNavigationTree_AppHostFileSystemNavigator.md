# ConfigPathTagNode::InitializeFileSystemChildren(ConfigPathNavigationTree *,AppHostFileSystemNavigator *)

- ea: `0x18000cc48`
- end: `0x18000cdca`
- name: `?InitializeFileSystemChildren@ConfigPathTagNode@@AEAAXPEAVConfigPathNavigationTree@@PEAVAppHostFileSystemNavigator@@@Z`
- size: `386`
- prototype: `void __fastcall(ConfigPathTagNode *__hidden this, struct ConfigPathNavigationTree *, struct AppHostFileSystemNavigator *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000d920`

## callees

- `0x1800039ec`
- `0x180005dc8`
- `0x18000c9bc`
- `0x18000cc48`
- `0x180012f3c`
- `0x180014010`

## string_xrefs

- `0x18000cd05`: `ConfigPathNodeType_File`
- `0x18000cd1d`: `ConfigPathNodeType_Directory`

## pseudocode

```c
void __fastcall ConfigPathTagNode::InitializeFileSystemChildren(
        ConfigPathTagNode *this,
        struct ConfigPathNavigationTree *a2,
        struct AppHostFileSystemNavigator *a3)
{
  int i; // eax
  int v7; // eax
  int v8; // eax
  __int64 v9; // rbx
  int v10; // eax
  int *v11; // r9
  __int64 InstanceAtRelativePath; // rax
  _QWORD *v13; // rdi
  __int64 v14; // [rsp+20h] [rbp-30h] BYREF
  __int64 v15; // [rsp+28h] [rbp-28h] BYREF
  int v16; // [rsp+30h] [rbp-20h] BYREF
  const wchar_t *v17; // [rsp+38h] [rbp-18h]
  int v18; // [rsp+40h] [rbp-10h] BYREF
  const wchar_t *v19; // [rsp+48h] [rbp-8h]
  int v20; // [rsp+90h] [rbp+40h] BYREF
  int pExceptionObject; // [rsp+98h] [rbp+48h] BYREF

  for ( i = (*(__int64 (__fastcall **)(struct AppHostFileSystemNavigator *, _QWORD, _QWORD))(*(_QWORD *)a3 + 136LL))(
              a3,
              0,
              0);
        ;
        i = (*(__int64 (__fastcall **)(struct AppHostFileSystemNavigator *, _QWORD, _QWORD))(*(_QWORD *)a3 + 152LL))(
              a3,
              0,
              0) )
  {
    if ( i < 0 )
    {
      pExceptionObject = i;
      throw (long *)&pExceptionObject;
    }
    if ( i )
      break;
    v14 = 0;
    v7 = (*(__int64 (__fastcall **)(struct AppHostFileSystemNavigator *, __int64 *))(*(_QWORD *)a3 + 64LL))(a3, &v14);
    if ( v7 < 0 )
    {
      pExceptionObject = v7;
      throw (long *)&pExceptionObject;
    }
    v15 = 0;
    v8 = AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::Clone(
           a3,
           &v15);
    if ( v8 < 0 )
    {
      pExceptionObject = v8;
      throw (long *)&pExceptionObject;
    }
    v20 = 0;
    v9 = v15;
    v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)(v15 + 8) + 144LL))(v15 + 8, &v20);
    if ( v10 < 0 )
    {
      pExceptionObject = v10;
      throw (long *)&pExceptionObject;
    }
    if ( v20 == 2 )
    {
      v16 = 9;
      v17 = L"ConfigPathNodeType_File";
      v11 = &v16;
    }
    else
    {
      v18 = 8;
      v19 = L"ConfigPathNodeType_Directory";
      v11 = &v18;
    }
    InstanceAtRelativePath = ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(this, a2, v14, v11);
    v13 = (_QWORD *)(InstanceAtRelativePath + 32);
    if ( *(_QWORD *)(InstanceAtRelativePath + 32) != v9 )
    {
      if ( v9 )
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 24));
      InvasivePtr<AppHostConfigPathNavigator>::Reset(InstanceAtRelativePath + 32);
      *v13 = v9;
    }
    InvasivePtr<AppHostConfigPathNavigator>::Reset(&v15);
  }
}

```

## disassembly

```asm
0x18000cc48  mov     [rsp-28h+arg_0], rbx
0x18000cc4d  push    rbp
0x18000cc4e  push    rsi
0x18000cc4f  push    rdi
0x18000cc50  push    r14
0x18000cc52  push    r15
0x18000cc54  mov     rbp, rsp
0x18000cc57  sub     rsp, 50h
0x18000cc5b  mov     rsi, r8
0x18000cc5e  mov     r14, rdx
0x18000cc61  mov     r15, rcx
0x18000cc64  mov     rax, [r8]
0x18000cc67  mov     rax, [rax+88h]
0x18000cc6e  xor     r8d, r8d
0x18000cc71  xor     edx, edx
0x18000cc73  mov     rcx, rsi
0x18000cc76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc7b  test    eax, eax
0x18000cc7d  js      loc_18000CDA2
0x18000cc83  jnz     loc_18000CDB6
0x18000cc89  mov     [rbp+var_30], 0
0x18000cc91  mov     rax, [rsi]
0x18000cc94  lea     rdx, [rbp+var_30]
0x18000cc98  mov     rcx, rsi
0x18000cc9b  mov     rax, [rax+40h]
0x18000cc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cca4  test    eax, eax
0x18000cca6  js      loc_18000CD8E
0x18000ccac  mov     [rbp+var_28], 0
0x18000ccb4  lea     rdx, [rbp+var_28]
0x18000ccb8  mov     rcx, rsi
0x18000ccbb  call    ?Clone@?$AppHostNavigatorTemplate@VAppHostFileSystemNavigator@@UIAppHostFileSystemNavigator@@VFileSystemTree@@@@QEAAJPEAPEAVAppHostFileSystemNavigator@@@Z; AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::Clone(AppHostFileSystemNavigator * *)
0x18000ccc0  test    eax, eax
0x18000ccc2  js      loc_18000CD7A
0x18000ccc8  mov     [rbp+arg_10], 0
0x18000cccf  mov     rbx, [rbp+var_28]
0x18000ccd3  lea     rcx, [rbx+8]
0x18000ccd7  mov     rax, [rcx]
0x18000ccda  lea     rdx, [rbp+arg_10]
0x18000ccde  mov     rax, [rax+90h]
0x18000cce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccea  test    eax, eax
0x18000ccec  js      short loc_18000CD66
0x18000ccee  mov     r8, [rbp+var_30]
0x18000ccf2  mov     rdx, r14
0x18000ccf5  mov     rcx, r15
0x18000ccf8  cmp     [rbp+arg_10], 2
0x18000ccfc  jnz     short loc_18000CD16
0x18000ccfe  mov     [rbp+var_20], 9
0x18000cd05  lea     rax, aConfigpathnode_5; "ConfigPathNodeType_File"
0x18000cd0c  mov     [rbp+var_18], rax
0x18000cd10  lea     r9, [rbp+var_20]
0x18000cd14  jmp     short loc_18000CD2C
0x18000cd16  mov     [rbp+var_10], 8
0x18000cd1d  lea     rax, aConfigpathnode_0; "ConfigPathNodeType_Directory"
0x18000cd24  mov     [rbp+var_8], rax
0x18000cd28  lea     r9, [rbp+var_10]
0x18000cd2c  call    ?GetOrCreateInstanceAtRelativePath@ConfigPathTagNode@@QEAAPEAV1@PEAVConfigPathNavigationTree@@PEBGAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(ConfigPathNavigationTree *,ushort const *,NamedEnum<ConfigPathNodeType> &)
0x18000cd31  lea     rdi, [rax+20h]
0x18000cd35  cmp     [rdi], rbx
0x18000cd38  jz      short loc_18000CD4E
0x18000cd3a  test    rbx, rbx
0x18000cd3d  jz      short loc_18000CD43
0x18000cd3f  lock inc dword ptr [rbx+18h]
0x18000cd43  mov     rcx, rdi
0x18000cd46  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x18000cd4b  mov     [rdi], rbx
0x18000cd4e  lea     rcx, [rbp+var_28]
0x18000cd52  call    ?Reset@?$InvasivePtr@VAppHostConfigPathNavigator@@@@QEAAXXZ; InvasivePtr<AppHostConfigPathNavigator>::Reset(void)
0x18000cd57  mov     rax, [rsi]
0x18000cd5a  mov     rax, [rax+98h]
0x18000cd61  jmp     loc_18000CC6E
0x18000cd66  mov     [rbp+pExceptionObject], eax
0x18000cd69  lea     rdx, _TI1J; pThrowInfo
0x18000cd70  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000cd74  call    _CxxThrowException_0
0x18000cd7a  mov     [rbp+pExceptionObject], eax
0x18000cd7d  lea     rdx, _TI1J; pThrowInfo
0x18000cd84  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000cd88  call    _CxxThrowException_0
0x18000cd8e  mov     [rbp+pExceptionObject], eax
0x18000cd91  lea     rdx, _TI1J; pThrowInfo
0x18000cd98  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000cd9c  call    _CxxThrowException_0
0x18000cda2  mov     [rbp+pExceptionObject], eax
0x18000cda5  lea     rdx, _TI1J; pThrowInfo
0x18000cdac  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000cdb0  call    _CxxThrowException_0
0x18000cdb6  mov     rbx, [rsp+50h+arg_0]
0x18000cdbe  add     rsp, 50h
0x18000cdc2  pop     r15
0x18000cdc4  pop     r14
0x18000cdc6  pop     rdi
0x18000cdc7  pop     rsi
0x18000cdc8  pop     rbp
0x18000cdc9  retn
```
