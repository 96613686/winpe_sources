# WofPreFsctlDeleteExternalBacking

- ea: `0x14003e870`
- end: `0x14003e9e3`
- name: `WofPreFsctlDeleteExternalBacking`
- size: `371`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140034740`

## callees

- `0x14000a914`
- `0x14000e3dc`
- `0x14000f3d4`
- `0x140034fa0`
- `0x140036954`
- `0x14003e870`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003e9ac`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003e9ac`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003e972`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003e972`
- `FLTMGR!FltGetStreamContext` at `0x14003e8a5`
- `FLTMGR!FltGetStreamContext` at `0x14003e8a5`
- `FLTMGR!FltReleaseContext` at `0x14003e934`
- `FLTMGR!FltReleaseContext` at `0x14003e9c1`
- `FLTMGR!FltReleaseContext` at `0x14003e934`
- `FLTMGR!FltReleaseContext` at `0x14003e9c1`

## pseudocode

```c
__int64 __fastcall WofPreFsctlDeleteExternalBacking(__int64 a1, __int64 a2, __int64 a3)
{
  struct _FILE_OBJECT *v4; // rdx
  BOOLEAN IsAdmin; // al
  int v7; // edx
  PFLT_CONTEXT v8; // rcx
  int v10; // eax
  PFLT_CONTEXT v11; // rcx
  int v12; // eax
  PFLT_CONTEXT Context; // [rsp+48h] [rbp+18h] BYREF
  __int64 v14; // [rsp+50h] [rbp+20h] BYREF

  v14 = a3;
  Context = 0;
  v4 = *(struct _FILE_OBJECT **)(a2 + 32);
  LOBYTE(v14) = 0;
  if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), v4, &Context) >= 0 )
  {
    if ( (int)WofIsDataInFilesystemEx(Context, (_QWORD *)a2, (bool *)&v14, 0) >= 0 && !(_BYTE)v14 )
    {
      IsAdmin = WofUserIsAdmin();
      v8 = Context;
      if ( IsAdmin || *((_DWORD *)Context + 3) != 1 )
      {
        v10 = WofEnsureExtdFileContext(*(_QWORD *)Context);
        v8 = Context;
        if ( v10 < 0 )
        {
          *(_DWORD *)(a1 + 24) = v10;
          goto LABEL_9;
        }
        WofEnsureExtdFileContext(*(_QWORD *)Context);
        ExAcquireFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context + 16LL));
        v11 = Context;
        if ( (*((_DWORD *)Context + 2) & 4) != 0 )
        {
          v12 = 0;
        }
        else
        {
          v12 = WofInflateFile(a1, a2, Context, 1);
          v11 = Context;
        }
        *(_DWORD *)(a1 + 24) = v12;
        ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)v11 + 16LL));
      }
      else
      {
        *(_DWORD *)(a1 + 24) = -1073741790;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_9:
          FltReleaseContext(v8);
          return 4;
        }
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v7,
          7,
          10,
          (__int64)WPP_dcfac5c580c33e55513b631fbc558444_Traceguids);
      }
      v8 = Context;
      goto LABEL_9;
    }
    FltReleaseContext(Context);
  }
  return 5;
}

```

## disassembly

```asm
0x14003e870  mov     [rsp-8+arg_0], rbx
0x14003e875  mov     [rsp-8+arg_18], rdi
0x14003e87a  mov     [rsp-8+arg_10], r8
0x14003e87f  push    rbp
0x14003e880  mov     rbp, rsp
0x14003e883  sub     rsp, 30h
0x14003e887  mov     rdi, rdx
0x14003e88a  mov     [rbp+Context], 0
0x14003e892  mov     rdx, [rdx+20h]; FileObject
0x14003e896  lea     r8, [rbp+Context]; Context
0x14003e89a  mov     rbx, rcx
0x14003e89d  mov     byte ptr [rbp+arg_10], 0
0x14003e8a1  mov     rcx, [rdi+18h]; Instance
0x14003e8a5  call    cs:__imp_FltGetStreamContext
0x14003e8ac  nop     dword ptr [rax+rax+00h]
0x14003e8b1  test    eax, eax
0x14003e8b3  js      loc_14003E9CD
0x14003e8b9  mov     rcx, [rbp+Context]
0x14003e8bd  lea     r8, [rbp+arg_10]
0x14003e8c1  xor     r9d, r9d
0x14003e8c4  mov     rdx, rdi
0x14003e8c7  call    WofIsDataInFilesystemEx
0x14003e8cc  test    eax, eax
0x14003e8ce  js      loc_14003E9BD
0x14003e8d4  cmp     byte ptr [rbp+arg_10], 0
0x14003e8d8  jnz     loc_14003E9BD
0x14003e8de  call    WofUserIsAdmin
0x14003e8e3  mov     rcx, [rbp+Context]
0x14003e8e7  test    al, al
0x14003e8e9  jnz     short loc_14003E94A
0x14003e8eb  cmp     dword ptr [rcx+0Ch], 1
0x14003e8ef  jnz     short loc_14003E94A
0x14003e8f1  mov     dword ptr [rbx+18h], 0C0000022h
0x14003e8f8  lea     rax, WPP_RECORDER_INITIALIZED
0x14003e8ff  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003e906  jz      short loc_14003E934
0x14003e908  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e90f  lea     rax, WPP_dcfac5c580c33e55513b631fbc558444_Traceguids
0x14003e916  mov     r9d, 0Ah
0x14003e91c  mov     [rsp+30h+var_10], rax
0x14003e921  mov     dl, 2
0x14003e923  mov     rcx, [rcx+40h]
0x14003e927  lea     r8d, [r9-3]
0x14003e92b  call    WPP_RECORDER_SF_
0x14003e930  mov     rcx, [rbp+Context]; Context
0x14003e934  call    cs:__imp_FltReleaseContext
0x14003e93b  nop     dword ptr [rax+rax+00h]
0x14003e940  mov     eax, 4
0x14003e945  jmp     loc_14003E9D2
0x14003e94a  mov     rcx, [rcx]
0x14003e94d  call    WofEnsureExtdFileContext
0x14003e952  mov     rcx, [rbp+Context]
0x14003e956  test    eax, eax
0x14003e958  jns     short loc_14003E95F
0x14003e95a  mov     [rbx+18h], eax
0x14003e95d  jmp     short loc_14003E934
0x14003e95f  mov     rcx, [rcx]
0x14003e962  call    WofEnsureExtdFileContext
0x14003e967  mov     rax, [rbp+Context]
0x14003e96b  mov     rcx, [rax]
0x14003e96e  mov     rcx, [rcx+10h]; FastMutex
0x14003e972  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003e979  nop     dword ptr [rax+rax+00h]
0x14003e97e  mov     rcx, [rbp+Context]
0x14003e982  mov     eax, [rcx+8]
0x14003e985  test    al, 4
0x14003e987  jnz     short loc_14003E9A0
0x14003e989  mov     r8, rcx
0x14003e98c  mov     r9b, 1
0x14003e98f  mov     rcx, rbx
0x14003e992  mov     rdx, rdi
0x14003e995  call    WofInflateFile
0x14003e99a  mov     rcx, [rbp+Context]
0x14003e99e  jmp     short loc_14003E9A2
0x14003e9a0  xor     eax, eax
0x14003e9a2  mov     [rbx+18h], eax
0x14003e9a5  mov     rcx, [rcx]
0x14003e9a8  mov     rcx, [rcx+10h]; FastMutex
0x14003e9ac  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003e9b3  nop     dword ptr [rax+rax+00h]
0x14003e9b8  jmp     loc_14003E930
0x14003e9bd  mov     rcx, [rbp+Context]; Context
0x14003e9c1  call    cs:__imp_FltReleaseContext
0x14003e9c8  nop     dword ptr [rax+rax+00h]
0x14003e9cd  mov     eax, 5
0x14003e9d2  mov     rbx, [rsp+30h+arg_0]
0x14003e9d7  mov     rdi, [rsp+30h+arg_18]
0x14003e9dc  add     rsp, 30h
0x14003e9e0  pop     rbp
0x14003e9e1  retn
```
