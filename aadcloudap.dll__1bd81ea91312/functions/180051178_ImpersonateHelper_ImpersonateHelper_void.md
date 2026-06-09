# ImpersonateHelper::~ImpersonateHelper(void)

- ea: `0x180051178`
- end: `0x1800511b9`
- name: `??1ImpersonateHelper@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800513d0`
- `0x1800a5388`

## callees

- `0x180051178`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180051191`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800511ad`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180051191`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800511ad`
- `ntdll!NtClose` at `0x18005119a`
- `ntdll!NtClose` at `0x18005119a`

## pseudocode

```c
void __fastcall ImpersonateHelper::~ImpersonateHelper(HANDLE *this)
{
  if ( *((_BYTE *)this + 8) )
  {
    if ( *this )
    {
      SetThreadToken(0, *this);
      NtClose(*this);
      *this = 0;
    }
    else
    {
      SetThreadToken(0, 0);
    }
  }
}

```

## disassembly

```asm
0x180051178  push    rbx
0x18005117a  sub     rsp, 20h
0x18005117e  cmp     byte ptr [rcx+8], 0
0x180051182  mov     rbx, rcx
0x180051185  jz      short loc_1800511B3
0x180051187  mov     rdx, [rcx]; Token
0x18005118a  xor     ecx, ecx; Thread
0x18005118c  test    rdx, rdx
0x18005118f  jz      short loc_1800511AD
0x180051191  call    cs:__imp_SetThreadToken
0x180051197  mov     rcx, [rbx]; Handle
0x18005119a  call    cs:__imp_NtClose
0x1800511a0  mov     qword ptr [rbx], 0
0x1800511a7  add     rsp, 20h
0x1800511ab  pop     rbx
0x1800511ac  retn
0x1800511ad  call    cs:__imp_SetThreadToken
0x1800511b3  add     rsp, 20h
0x1800511b7  pop     rbx
0x1800511b8  retn
```
