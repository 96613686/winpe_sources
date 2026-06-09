# CDtcService::Install(ulong,ushort *,int)

- ea: `0x180083b40`
- end: `0x180083c71`
- name: `?Install@CDtcService@@UEAAJKPEAGH@Z`
- size: `305`
- prototype: `__int64 __fastcall(CDtcService *__hidden this, unsigned int, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180014c68`
- `0x180015230`
- `0x180083b40`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `MSDTCPRX!CreateLocalTmInstance` at `0x180083b79`
- `MSDTCPRX!CreateLocalTmInstance` at `0x180083b79`
- `MSDTCPRX!InstallDtc` at `0x180083bd8`
- `MSDTCPRX!InstallDtc` at `0x180083bd8`

## string_xrefs

- `0x180083b92`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x180083b8b`: `CNTService::InstallDtc failed`
- `0x180083c39`: `CNTService::InitLog failed`

## pseudocode

```c
__int64 __fastcall CDtcService::Install(CDtcService *this, __int64 a2, unsigned __int16 *a3)
{
  int inited; // ebx
  unsigned int v5; // r9d
  char *v6; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  struct ITmInstance *v10; // [rsp+50h] [rbp-448h] BYREF
  unsigned __int16 v11[512]; // [rsp+60h] [rbp-438h] BYREF

  v10 = 0;
  inited = CreateLocalTmInstance(&v10);
  if ( inited < 0 )
  {
    v5 = 174;
LABEL_3:
    v6 = "CNTService::InstallDtc failed";
LABEL_4:
    TraceFile(inited, v6, "com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp", v5);
    return (unsigned int)inited;
  }
  inited = InstallDtc(v10, *((_QWORD *)this + 1), *((_QWORD *)this + 2), *((_QWORD *)this + 3));
  if ( inited < 0 )
  {
    (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v10 + 16LL))(v10);
    v5 = 193;
    goto LABEL_3;
  }
  inited = InitLog(v10, v11, v8, v9, (unsigned int)v11, 0x400000u, 1, 1);
  if ( inited )
  {
    (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v10 + 16LL))(v10);
    v5 = 214;
    v6 = "CNTService::InitLog failed";
    goto LABEL_4;
  }
  (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v10 + 16LL))(v10);
  return 0;
}

```

## disassembly

```asm
0x180083b40  push    rbx
0x180083b42  push    rbp
0x180083b43  push    rsi
0x180083b44  push    rdi
0x180083b45  push    r14
0x180083b47  sub     rsp, 470h
0x180083b4e  mov     rax, cs:__security_cookie
0x180083b55  xor     rax, rsp
0x180083b58  mov     [rsp+498h+var_38], rax
0x180083b60  mov     rdi, rcx
0x180083b63  mov     [rsp+498h+var_448], 0
0x180083b6c  lea     rcx, [rsp+498h+var_448]
0x180083b71  mov     r14d, r9d
0x180083b74  mov     rbp, r8
0x180083b77  mov     esi, edx
0x180083b79  call    cs:__imp_CreateLocalTmInstance
0x180083b7f  mov     ebx, eax
0x180083b81  test    eax, eax
0x180083b83  jns     short loc_180083BA7
0x180083b85  mov     r9d, 0AEh; unsigned int
0x180083b8b  lea     rdx, aCntserviceInst; "CNTService::InstallDtc failed"
0x180083b92  lea     r8, aComComplusDtcD_110; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x180083b99  mov     ecx, ebx; int
0x180083b9b  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180083ba0  mov     eax, ebx
0x180083ba2  jmp     loc_180083C53
0x180083ba7  mov     r9, [rdi+18h]
0x180083bab  lea     rax, [rsp+498h+var_438]
0x180083bb0  mov     r8, [rdi+10h]
0x180083bb4  mov     rdx, [rdi+8]
0x180083bb8  mov     rcx, [rsp+498h+var_448]
0x180083bbd  mov     [rsp+498h+var_458], r14d
0x180083bc2  mov     qword ptr [rsp+498h+var_460], rbp
0x180083bc7  mov     [rsp+498h+var_468], esi
0x180083bcb  mov     [rsp+498h+var_470], 200h
0x180083bd3  mov     qword ptr [rsp+498h+var_478], rax; unsigned int
0x180083bd8  call    cs:__imp_InstallDtc
0x180083bde  mov     rcx, [rsp+498h+var_448]; struct ITmInstance *
0x180083be3  mov     ebx, eax
0x180083be5  test    eax, eax
0x180083be7  jns     short loc_180083BFD
0x180083be9  mov     rdx, [rcx]
0x180083bec  mov     rax, [rdx+10h]
0x180083bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083bf5  mov     r9d, 0C1h
0x180083bfb  jmp     short loc_180083B8B
0x180083bfd  mov     eax, 1
0x180083c02  lea     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180083c07  mov     [rsp+498h+var_460], eax; int
0x180083c0b  mov     [rsp+498h+var_468], eax; int
0x180083c0f  mov     [rsp+498h+var_470], 400000h; unsigned int
0x180083c17  call    ?InitLog@@YAJPEAUITmInstance@@PEAGKKKKHH@Z; InitLog(ITmInstance *,ushort *,ulong,ulong,ulong,ulong,int,int)
0x180083c1c  mov     rcx, [rsp+498h+var_448]
0x180083c21  mov     ebx, eax
0x180083c23  test    eax, eax
0x180083c25  jz      short loc_180083C45
0x180083c27  mov     rdx, [rcx]
0x180083c2a  mov     rax, [rdx+10h]
0x180083c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c33  mov     r9d, 0D6h
0x180083c39  lea     rdx, aCntserviceInit; "CNTService::InitLog failed"
0x180083c40  jmp     loc_180083B92
0x180083c45  mov     rax, [rcx]
0x180083c48  mov     rax, [rax+10h]
0x180083c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c51  xor     eax, eax
0x180083c53  mov     rcx, [rsp+498h+var_38]
0x180083c5b  xor     rcx, rsp; StackCookie
0x180083c5e  call    __security_check_cookie
0x180083c63  add     rsp, 470h
0x180083c6a  pop     r14
0x180083c6c  pop     rdi
0x180083c6d  pop     rsi
0x180083c6e  pop     rbp
0x180083c6f  pop     rbx
0x180083c70  retn
```
