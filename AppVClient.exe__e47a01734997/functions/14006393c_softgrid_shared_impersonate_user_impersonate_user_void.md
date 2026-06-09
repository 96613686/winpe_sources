# softgrid::shared::impersonate_user::~impersonate_user(void)

- ea: `0x14006393c`
- end: `0x1400639c3`
- name: `??1impersonate_user@shared@softgrid@@QEAA@XZ`
- size: `135`
- prototype: `void __fastcall(softgrid::shared::impersonate_user *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400639cc`
- `0x1400640a4`
- `0x140068e2a`

## callees

- `0x14006393c`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x14006394e`
- `ADVAPI32!SetThreadToken` at `0x140063977`
- `ADVAPI32!SetThreadToken` at `0x14006394e`
- `ADVAPI32!SetThreadToken` at `0x140063977`
- `KERNEL32!RaiseException` at `0x140063966`
- `KERNEL32!RaiseException` at `0x1400639b7`
- `KERNEL32!RaiseException` at `0x140063966`
- `KERNEL32!RaiseException` at `0x1400639b7`
- `KERNEL32!CloseHandle` at `0x140063985`
- `KERNEL32!CloseHandle` at `0x1400639a2`
- `KERNEL32!CloseHandle` at `0x140063985`
- `KERNEL32!CloseHandle` at `0x1400639a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall softgrid::shared::impersonate_user::~impersonate_user(softgrid::shared::impersonate_user *this)
{
  void *v2; // rdx
  BOOL v3; // eax
  void *v4; // rcx

  if ( *(_DWORD *)this && !SetThreadToken(0, 0) )
    RaiseException(0x29Cu, 1u, 0, 0);
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    v3 = SetThreadToken(0, v2);
    v4 = (void *)*((_QWORD *)this + 2);
    if ( v3 )
    {
      CloseHandle(v4);
      *((_QWORD *)this + 2) = 0;
      *((_BYTE *)this + 8) = 0;
    }
    else
    {
      if ( v4 )
        CloseHandle(v4);
      RaiseException(0x29Cu, 1u, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x14006393c  push    rbx
0x14006393e  sub     rsp, 20h
0x140063942  cmp     dword ptr [rcx], 0
0x140063945  mov     rbx, rcx
0x140063948  jz      short loc_14006396C
0x14006394a  xor     edx, edx; Token
0x14006394c  xor     ecx, ecx; Thread
0x14006394e  call    cs:__imp_SetThreadToken
0x140063954  test    eax, eax
0x140063956  jnz     short loc_14006396C
0x140063958  xor     r9d, r9d; lpArguments
0x14006395b  lea     edx, [rax+1]; dwExceptionFlags
0x14006395e  xor     r8d, r8d; nNumberOfArguments
0x140063961  mov     ecx, 29Ch; dwExceptionCode
0x140063966  call    cs:__imp_RaiseException
0x14006396c  mov     rdx, [rbx+10h]; Token
0x140063970  test    rdx, rdx
0x140063973  jz      short loc_1400639BD
0x140063975  xor     ecx, ecx; Thread
0x140063977  call    cs:__imp_SetThreadToken
0x14006397d  mov     rcx, [rbx+10h]; hObject
0x140063981  test    eax, eax
0x140063983  jz      short loc_14006399D
0x140063985  call    cs:__imp_CloseHandle
0x14006398b  mov     qword ptr [rbx+10h], 0
0x140063993  mov     byte ptr [rbx+8], 0
0x140063997  add     rsp, 20h
0x14006399b  pop     rbx
0x14006399c  retn
0x14006399d  test    rcx, rcx
0x1400639a0  jz      short loc_1400639A8
0x1400639a2  call    cs:__imp_CloseHandle
0x1400639a8  xor     r9d, r9d; lpArguments
0x1400639ab  xor     r8d, r8d; nNumberOfArguments
0x1400639ae  mov     ecx, 29Ch; dwExceptionCode
0x1400639b3  lea     edx, [r9+1]; dwExceptionFlags
0x1400639b7  call    cs:__imp_RaiseException
0x1400639bd  add     rsp, 20h
0x1400639c1  pop     rbx
0x1400639c2  retn
```
