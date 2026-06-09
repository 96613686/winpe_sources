# CDbOperationManager::CImpersonateEseDbUser::~CImpersonateEseDbUser(void)

- ea: `0x1800e8410`
- end: `0x1800e84ea`
- name: `??1CImpersonateEseDbUser@CDbOperationManager@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(CDbOperationManager::CImpersonateEseDbUser *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800e85f4`
- `0x1800e8adc`
- `0x1800e8dc8`
- `0x1800e90e8`
- `0x1800e980c`
- `0x1800ea298`
- `0x1800ea844`
- `0x1800eaad0`
- `0x1800ead0c`

## callees

- `0x18002dad0`
- `0x180061674`
- `0x1800e8410`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e8441`
- `KERNEL32!GetLastError` at `0x1800e8491`
- `KERNEL32!GetLastError` at `0x1800e8441`
- `KERNEL32!GetLastError` at `0x1800e8491`
- `ADVAPI32!SetThreadToken` at `0x1800e8433`
- `ADVAPI32!SetThreadToken` at `0x1800e8487`
- `ADVAPI32!SetThreadToken` at `0x1800e8433`
- `ADVAPI32!SetThreadToken` at `0x1800e8487`

## pseudocode

```c
void __fastcall CDbOperationManager::CImpersonateEseDbUser::~CImpersonateEseDbUser(
        CDbOperationManager::CImpersonateEseDbUser *this)
{
  char *v2; // rdx
  char LastError; // al
  _QWORD *v4; // rcx
  int v5; // edx

  if ( *((int *)this + 4) >= 0 )
  {
    v2 = (char *)*((_QWORD *)this + 1);
    if ( (unsigned __int64)(v2 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( (unsigned __int64)(*(_QWORD *)(*(_QWORD *)this + 112LL) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL
        && !SetThreadToken(0, 0) )
      {
        LastError = GetLastError();
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v5 = 95;
          goto LABEL_12;
        }
      }
    }
    else if ( !SetThreadToken(0, v2) )
    {
      LastError = GetLastError();
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 94;
LABEL_12:
        WPP_SF_Sd(
          v4[2],
          v5,
          (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
          *(_QWORD *)(*(_QWORD *)this + 72LL),
          LastError);
      }
    }
  }
  CAutoHandle<void *>::~CAutoHandle<void *>((char *)this + 8);
}

```

## disassembly

```asm
0x1800e8410  push    rbx
0x1800e8412  sub     rsp, 30h
0x1800e8416  cmp     dword ptr [rcx+10h], 0
0x1800e841a  mov     rbx, rcx
0x1800e841d  jl      loc_1800E84DC
0x1800e8423  mov     rdx, [rcx+8]; Token
0x1800e8427  lea     rax, [rdx-1]
0x1800e842b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e842f  ja      short loc_1800E8473
0x1800e8431  xor     ecx, ecx; Thread
0x1800e8433  call    cs:__imp_SetThreadToken
0x1800e8439  test    eax, eax
0x1800e843b  jnz     loc_1800E84DC
0x1800e8441  call    cs:__imp_GetLastError
0x1800e8447  test    eax, eax
0x1800e8449  jle     short loc_1800E8453
0x1800e844b  movzx   eax, ax
0x1800e844e  or      eax, 80070000h
0x1800e8453  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e845a  lea     rdx, WPP_GLOBAL_Control
0x1800e8461  cmp     rcx, rdx
0x1800e8464  jz      short loc_1800E84DC
0x1800e8466  test    byte ptr [rcx+1Ch], 1
0x1800e846a  jz      short loc_1800E84DC
0x1800e846c  mov     edx, 5Eh ; '^'
0x1800e8471  jmp     short loc_1800E84C1
0x1800e8473  mov     rax, [rcx]
0x1800e8476  mov     rcx, [rax+70h]
0x1800e847a  dec     rcx
0x1800e847d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800e8481  ja      short loc_1800E84DC
0x1800e8483  xor     edx, edx; Token
0x1800e8485  xor     ecx, ecx; Thread
0x1800e8487  call    cs:__imp_SetThreadToken
0x1800e848d  test    eax, eax
0x1800e848f  jnz     short loc_1800E84DC
0x1800e8491  call    cs:__imp_GetLastError
0x1800e8497  test    eax, eax
0x1800e8499  jle     short loc_1800E84A3
0x1800e849b  movzx   eax, ax
0x1800e849e  or      eax, 80070000h
0x1800e84a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e84aa  lea     rdx, WPP_GLOBAL_Control
0x1800e84b1  cmp     rcx, rdx
0x1800e84b4  jz      short loc_1800E84DC
0x1800e84b6  test    byte ptr [rcx+1Ch], 1
0x1800e84ba  jz      short loc_1800E84DC
0x1800e84bc  mov     edx, 5Fh ; '_'
0x1800e84c1  mov     r9, [rbx]
0x1800e84c4  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e84cb  mov     rcx, [rcx+10h]
0x1800e84cf  mov     [rsp+38h+var_18], eax
0x1800e84d3  mov     r9, [r9+48h]
0x1800e84d7  call    WPP_SF_Sd
0x1800e84dc  lea     rcx, [rbx+8]
0x1800e84e0  add     rsp, 30h
0x1800e84e4  pop     rbx
0x1800e84e5  jmp     ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
```
