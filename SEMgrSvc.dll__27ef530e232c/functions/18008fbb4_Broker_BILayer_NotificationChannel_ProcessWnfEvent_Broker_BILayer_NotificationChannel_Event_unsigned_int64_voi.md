# Broker::BILayer::NotificationChannel::ProcessWnfEvent(Broker::BILayer::NotificationChannel::Event,unsigned __int64,void const *)

- ea: `0x18008fbb4`
- end: `0x18008fe25`
- name: `?ProcessWnfEvent@NotificationChannel@BILayer@Broker@@QEAAXW4Event@123@_KPEBX@Z`
- size: `625`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008fff0`
- `0x180090010`
- `0x180090070`
- `0x180090090`
- `0x1800900b0`
- `0x1800900d0`
- `0x1800900f0`

## callees

- `0x180005888`
- `0x18008b778`
- `0x18008ecf0`
- `0x18008fbb4`
- `0x1800902d0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008fc60`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008fc6d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008fd54`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008fc60`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008fc6d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18008fd54`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
void __fastcall Broker::BILayer::NotificationChannel::ProcessWnfEvent(
        __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        int *a4)
{
  __int64 v4; // rdi
  char *v6; // rsi
  char *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 *v10; // r9
  int v11; // r8d
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 *v15; // r8
  int v16; // esi
  int v17; // r15d
  __int64 v18; // r12
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // r10
  char *v22; // [rsp+30h] [rbp-78h] BYREF
  __int64 v23; // [rsp+38h] [rbp-70h] BYREF
  __int64 v24; // [rsp+40h] [rbp-68h] BYREF
  _BYTE pExceptionObject[96]; // [rsp+48h] [rbp-60h] BYREF
  int v26; // [rsp+C8h] [rbp+20h] BYREF

  v4 = (int)a2;
  if ( !a4 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, a3, a2);
    return;
  }
  if ( a2 < 2 )
  {
    if ( a3 < 0x18 )
      return;
    v16 = *a4;
    v17 = a4[4];
    v18 = *((_QWORD *)a4 + 1);
    v19 = (unsigned __int64)(a4 + 5) & -(__int64)IsValidSid(a4 + 5);
    v20 = *(_QWORD *)(a1 + 24);
    v21 = *(_QWORD *)((v4 << 8) + v20 + 184);
    if ( v21 )
    {
      v23 = v19;
      v26 = v17;
      v24 = v18;
      LODWORD(v22) = v16;
      (*(void (__fastcall **)(__int64, char **, __int64 *, int *, __int64 *))(*(_QWORD *)v21 + 16LL))(
        v21,
        &v22,
        &v24,
        &v26,
        &v23);
      return;
    }
    v9 = *(_QWORD *)((v4 << 8) + v20 + 56);
    if ( v9 )
    {
      v24 = v19;
      v23 = 0;
      v26 = v16;
      v10 = &v24;
LABEL_31:
      v15 = &v23;
      goto LABEL_32;
    }
  }
  else
  {
    if ( a2 != 2 && a2 != 3 )
    {
      if ( a2 != 4 && a2 - 5 > 1 )
        return;
      if ( a3 < 0xC )
      {
        Broker::InvalidParameter::InvalidParameter((Broker::InvalidParameter *)pExceptionObject);
        throw (Broker::InvalidParameter *)pExceptionObject;
      }
      if ( a4[1] )
        v6 = (char *)a4 + (unsigned int)a4[1];
      else
        v6 = 0;
      if ( *a4 )
      {
        v7 = (char *)a4 + (unsigned int)*a4;
        if ( IsValidSid(v7) )
        {
LABEL_19:
          v9 = *(_QWORD *)((v4 << 8) + *(_QWORD *)(a1 + 24) + 56);
          if ( !v9 )
            return;
          v22 = v7;
          v23 = (__int64)v6;
          v26 = -1;
          v10 = (__int64 *)&v22;
          goto LABEL_31;
        }
        if ( !IsValidSid(v7) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v8);
      }
      v7 = 0;
      goto LABEL_19;
    }
    if ( a3 < 4 )
      return;
    v11 = *a4;
    v12 = (__int64)(int)a2 << 8;
    v13 = *(_QWORD *)(a1 + 24);
    v14 = *(_QWORD *)((v4 << 8) + v13 + 248);
    if ( v14 )
    {
      v26 = *a4;
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 16LL))(v14, &v26);
      return;
    }
    v9 = *(_QWORD *)(v12 + v13 + 56);
    if ( v9 )
    {
      v22 = 0;
      v23 = 0;
      v26 = v11;
      v10 = &v23;
      v15 = (__int64 *)&v22;
LABEL_32:
      (*(void (__fastcall **)(__int64, int *, __int64 *, __int64 *))(*(_QWORD *)v9 + 16LL))(v9, &v26, v15, v10);
    }
  }
}

```

## disassembly

```asm
0x18008fbb4  push    rbx
0x18008fbb6  push    rsi
0x18008fbb7  push    rdi
0x18008fbb8  push    r12
0x18008fbba  push    r14
0x18008fbbc  push    r15
0x18008fbbe  sub     rsp, 78h
0x18008fbc2  movsxd  rdi, edx
0x18008fbc5  mov     r14, rcx
0x18008fbc8  test    r9, r9
0x18008fbcb  jnz     short loc_18008FBFD
0x18008fbcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18008fbd4  test    byte ptr [rcx+1Ch], 1
0x18008fbd8  jz      loc_18008FDFA
0x18008fbde  cmp     byte ptr [rcx+19h], 2
0x18008fbe2  jb      loc_18008FDFA
0x18008fbe8  lea     edx, [r9+28h]
0x18008fbec  mov     r9d, edi
0x18008fbef  mov     rcx, [rcx+10h]
0x18008fbf3  call    WPP_SF_d
0x18008fbf8  jmp     loc_18008FDFA
0x18008fbfd  mov     ecx, edi
0x18008fbff  test    edx, edx
0x18008fc01  jz      loc_18008FD38
0x18008fc07  sub     ecx, 1
0x18008fc0a  jz      loc_18008FD38
0x18008fc10  sub     ecx, 1
0x18008fc13  jz      loc_18008FCBB
0x18008fc19  sub     ecx, 1
0x18008fc1c  jz      loc_18008FCBB
0x18008fc22  sub     ecx, 1
0x18008fc25  jz      short loc_18008FC35
0x18008fc27  sub     ecx, 1
0x18008fc2a  jz      short loc_18008FC35
0x18008fc2c  cmp     ecx, 1
0x18008fc2f  jnz     loc_18008FDFA
0x18008fc35  cmp     r8, 0Ch
0x18008fc39  jb      loc_18008FE08
0x18008fc3f  cmp     dword ptr [r9+4], 0
0x18008fc44  jz      short loc_18008FC4F
0x18008fc46  mov     esi, [r9+4]
0x18008fc4a  add     rsi, r9
0x18008fc4d  jmp     short loc_18008FC51
0x18008fc4f  xor     esi, esi
0x18008fc51  cmp     dword ptr [r9], 0
0x18008fc55  jz      short loc_18008FC7C
0x18008fc57  mov     ebx, [r9]
0x18008fc5a  add     rbx, r9
0x18008fc5d  mov     rcx, rbx; pSid
0x18008fc60  call    cs:__imp_IsValidSid
0x18008fc66  test    eax, eax
0x18008fc68  jnz     short loc_18008FC7E
0x18008fc6a  mov     rcx, rbx; pSid
0x18008fc6d  call    cs:__imp_IsValidSid
0x18008fc73  test    eax, eax
0x18008fc75  jnz     short loc_18008FC7C
0x18008fc77  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008fc7c  xor     ebx, ebx
0x18008fc7e  mov     rcx, rdi
0x18008fc81  shl     rcx, 8
0x18008fc85  mov     rax, [r14+18h]
0x18008fc89  mov     rcx, [rcx+rax+38h]
0x18008fc8e  test    rcx, rcx
0x18008fc91  jz      loc_18008FDFA
0x18008fc97  mov     [rsp+0A8h+var_78], rbx
0x18008fc9c  mov     [rsp+0A8h+var_70], rsi
0x18008fca1  mov     [rsp+0A8h+arg_18], 0FFFFFFFFh
0x18008fcac  lea     r9, [rsp+0A8h+var_78]
0x18008fcb1  jmp     loc_18008FDE1
0x18008fcb6  jmp     loc_18008FDFA
0x18008fcbb  cmp     r8, 4
0x18008fcbf  jb      loc_18008FDFA
0x18008fcc5  mov     r8d, [r9]
0x18008fcc8  mov     rax, rdi
0x18008fccb  shl     rax, 8
0x18008fccf  mov     rdx, [r14+18h]
0x18008fcd3  mov     rcx, [rax+rdx+0F8h]
0x18008fcdb  test    rcx, rcx
0x18008fcde  jz      short loc_18008FD01
0x18008fce0  mov     [rsp+0A8h+arg_18], r8d
0x18008fce8  mov     rax, [rcx]
0x18008fceb  lea     rdx, [rsp+0A8h+arg_18]
0x18008fcf3  mov     rax, [rax+10h]
0x18008fcf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fcfc  jmp     loc_18008FDFA
0x18008fd01  mov     rcx, [rax+rdx+38h]
0x18008fd06  test    rcx, rcx
0x18008fd09  jz      loc_18008FDFA
0x18008fd0f  mov     [rsp+0A8h+var_78], 0
0x18008fd18  mov     [rsp+0A8h+var_70], 0
0x18008fd21  mov     [rsp+0A8h+arg_18], r8d
0x18008fd29  lea     r9, [rsp+0A8h+var_70]
0x18008fd2e  lea     r8, [rsp+0A8h+var_78]
0x18008fd33  jmp     loc_18008FDE6
0x18008fd38  cmp     r8, 18h
0x18008fd3c  jb      loc_18008FDFA
0x18008fd42  mov     esi, [r9]
0x18008fd45  mov     r15d, [r9+10h]
0x18008fd49  mov     r12, [r9+8]
0x18008fd4d  lea     rbx, [r9+14h]
0x18008fd51  mov     rcx, rbx; pSid
0x18008fd54  call    cs:__imp_IsValidSid
0x18008fd5a  neg     eax
0x18008fd5c  sbb     rdx, rdx
0x18008fd5f  and     rdx, rbx
0x18008fd62  mov     rcx, rdi
0x18008fd65  shl     rcx, 8
0x18008fd69  mov     rax, [r14+18h]
0x18008fd6d  mov     r10, [rcx+rax+0B8h]
0x18008fd75  test    r10, r10
0x18008fd78  jz      short loc_18008FDBD
0x18008fd7a  mov     [rsp+0A8h+var_70], rdx
0x18008fd7f  mov     [rsp+0A8h+arg_18], r15d
0x18008fd87  mov     [rsp+0A8h+var_68], r12
0x18008fd8c  mov     dword ptr [rsp+0A8h+var_78], esi
0x18008fd90  mov     rax, [r10]
0x18008fd93  lea     rcx, [rsp+0A8h+var_70]
0x18008fd98  mov     [rsp+0A8h+var_88], rcx
0x18008fd9d  lea     r9, [rsp+0A8h+arg_18]
0x18008fda5  lea     r8, [rsp+0A8h+var_68]
0x18008fdaa  lea     rdx, [rsp+0A8h+var_78]
0x18008fdaf  mov     rcx, r10
0x18008fdb2  mov     rax, [rax+10h]
0x18008fdb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fdbb  jmp     short loc_18008FDFA
0x18008fdbd  mov     rcx, [rcx+rax+38h]
0x18008fdc2  test    rcx, rcx
0x18008fdc5  jz      short loc_18008FDFA
0x18008fdc7  mov     [rsp+0A8h+var_68], rdx
0x18008fdcc  mov     [rsp+0A8h+var_70], 0
0x18008fdd5  mov     [rsp+0A8h+arg_18], esi
0x18008fddc  lea     r9, [rsp+0A8h+var_68]
0x18008fde1  lea     r8, [rsp+0A8h+var_70]
0x18008fde6  mov     rax, [rcx]
0x18008fde9  lea     rdx, [rsp+0A8h+arg_18]
0x18008fdf1  mov     rax, [rax+10h]
0x18008fdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fdfa  add     rsp, 78h
0x18008fdfe  pop     r15
0x18008fe00  pop     r14
0x18008fe02  pop     r12
0x18008fe04  pop     rdi
0x18008fe05  pop     rsi
0x18008fe06  pop     rbx
0x18008fe07  retn
0x18008fe08  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x18008fe0d  call    ??0InvalidParameter@Broker@@QEAA@XZ; Broker::InvalidParameter::InvalidParameter(void)
0x18008fe12  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18008fe19  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18008fe1e  call    _CxxThrowException_0
```
