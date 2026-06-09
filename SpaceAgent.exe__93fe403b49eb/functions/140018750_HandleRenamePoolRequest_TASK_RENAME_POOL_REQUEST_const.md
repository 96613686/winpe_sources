# HandleRenamePoolRequest(TASK_RENAME_POOL_REQUEST const *)

- ea: `0x140018750`
- end: `0x1400188aa`
- name: `?HandleRenamePoolRequest@@YAHPEBUTASK_RENAME_POOL_REQUEST@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(const struct TASK_RENAME_POOL_REQUEST *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140017d70`

## callees

- `0x140008190`
- `0x14000a440`
- `0x14000a5e0`
- `0x14000a6f8`
- `0x14001832c`
- `0x140018750`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140018874`
- `KERNEL32!LocalFree` at `0x140018874`
- `KERNEL32!SetLastError` at `0x14001878b`
- `KERNEL32!SetLastError` at `0x140018892`
- `KERNEL32!SetLastError` at `0x14001878b`
- `KERNEL32!SetLastError` at `0x140018892`
- `KERNEL32!GetLastError` at `0x140018864`
- `KERNEL32!GetLastError` at `0x140018888`
- `KERNEL32!GetLastError` at `0x140018864`
- `KERNEL32!GetLastError` at `0x140018888`
- `KERNEL32!DeviceIoControl` at `0x14001885c`
- `KERNEL32!DeviceIoControl` at `0x14001885c`

## pseudocode

```c
__int64 __fastcall HandleRenamePoolRequest(const struct TASK_RENAME_POOL_REQUEST *a1)
{
  struct _SU_POOL_OBJECT *v2; // rdi
  unsigned int IsPoolCompatible; // ebx
  DWORD v4; // ecx
  unsigned int Pool; // eax
  unsigned __int16 *v6; // rcx
  DWORD LastError; // esi
  HLOCAL v8; // rax
  struct _SU_POOL_OBJECT *BytesReturned; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  BytesReturned = 0;
  IsPoolCompatible = IssueProgressStringResult(32887);
  if ( IsPoolCompatible )
  {
    if ( *(_QWORD *)a1 != 544 )
    {
      IsPoolCompatible = 0;
      v4 = 24;
LABEL_4:
      SetLastError(v4);
      goto LABEL_13;
    }
    Pool = SiGetPool((struct _GUID *)a1 + 1, 0, &BytesReturned);
    v2 = BytesReturned;
    IsPoolCompatible = Pool;
    if ( !Pool )
      goto LABEL_13;
    v6 = (unsigned __int16 *)((char *)BytesReturned + 80);
    *((_WORD *)a1 + 271) = 0;
    v4 = StringCchCopyW(v6, 0x100u, (const unsigned __int16 *)a1 + 16);
    if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147024774 )
    {
      IsPoolCompatible = 0;
      if ( (v4 & 0x1FFF0000) == 0x70000 )
        v4 = (unsigned __int16)v4;
      goto LABEL_4;
    }
    LODWORD(BytesReturned) = 0;
    IsPoolCompatible = SiValidatePool((struct _SU_POOL_OBJECT *)((char *)v2 + 56), 0);
    if ( IsPoolCompatible )
    {
      IsPoolCompatible = SiIsPoolCompatible((struct _SU_POOL_OBJECT *)((char *)v2 + 56));
      if ( IsPoolCompatible )
        IsPoolCompatible = DeviceIoControl(
                             Spaceport,
                             0xE7C00Cu,
                             (char *)v2 + 56,
                             *((_DWORD *)v2 + 15),
                             0,
                             0,
                             (LPDWORD)&BytesReturned,
                             0);
    }
  }
LABEL_13:
  LastError = GetLastError();
  if ( v2 )
  {
    v8 = LocalFree(v2);
    if ( IsPoolCompatible )
    {
      IsPoolCompatible = v8 == 0;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return IsPoolCompatible;
}

```

## disassembly

```asm
0x140018750  mov     [rsp+arg_8], rbx
0x140018755  mov     [rsp+arg_10], rsi
0x14001875a  push    rdi
0x14001875b  sub     rsp, 40h
0x14001875f  mov     rsi, rcx
0x140018762  xor     edi, edi
0x140018764  mov     ecx, 8077h
0x140018769  mov     [rsp+48h+BytesReturned], rdi
0x14001876e  call    IssueProgressStringResult
0x140018773  mov     ebx, eax
0x140018775  test    eax, eax
0x140018777  jz      loc_140018864
0x14001877d  cmp     qword ptr [rsi], 220h
0x140018784  jz      short loc_140018796
0x140018786  xor     ebx, ebx
0x140018788  lea     ecx, [rdi+18h]; dwErrCode
0x14001878b  call    cs:__imp_SetLastError
0x140018791  jmp     loc_140018864
0x140018796  lea     rcx, [rsi+10h]; struct _GUID *
0x14001879a  xor     edx, edx; unsigned int
0x14001879c  lea     r8, [rsp+48h+BytesReturned]; struct _SU_POOL_OBJECT **
0x1400187a1  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x1400187a6  mov     rdi, [rsp+48h+BytesReturned]
0x1400187ab  mov     ebx, eax
0x1400187ad  test    eax, eax
0x1400187af  jz      loc_140018864
0x1400187b5  lea     r8, [rsi+20h]; unsigned __int16 *
0x1400187b9  xor     eax, eax
0x1400187bb  lea     rcx, [rdi+50h]; unsigned __int16 *
0x1400187bf  mov     [r8+1FEh], ax
0x1400187c7  mov     edx, 100h; unsigned __int64
0x1400187cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400187d1  mov     edx, 80000000h
0x1400187d6  mov     ecx, eax
0x1400187d8  add     eax, edx
0x1400187da  test    edx, eax
0x1400187dc  jnz     short loc_1400187FB
0x1400187de  cmp     ecx, 8007007Ah
0x1400187e4  jz      short loc_1400187FB
0x1400187e6  mov     eax, ecx
0x1400187e8  xor     ebx, ebx
0x1400187ea  and     eax, 1FFF0000h
0x1400187ef  cmp     eax, 70000h
0x1400187f4  jnz     short loc_14001878B
0x1400187f6  movzx   ecx, cx
0x1400187f9  jmp     short loc_14001878B
0x1400187fb  lea     rsi, [rdi+38h]
0x1400187ff  mov     dword ptr [rsp+48h+BytesReturned], 0
0x140018807  mov     rcx, rsi; struct _SP_POOL_INFO *
0x14001880a  xor     edx, edx; int
0x14001880c  call    ?SiValidatePool@@YAHPEAU_SP_POOL_INFO@@H@Z; SiValidatePool(_SP_POOL_INFO *,int)
0x140018811  mov     ebx, eax
0x140018813  test    eax, eax
0x140018815  jz      short loc_140018864
0x140018817  mov     rcx, rsi; struct _SP_POOL_INFO *
0x14001881a  call    ?SiIsPoolCompatible@@YAHPEAU_SP_POOL_INFO@@@Z; SiIsPoolCompatible(_SP_POOL_INFO *)
0x14001881f  mov     ebx, eax
0x140018821  test    eax, eax
0x140018823  jz      short loc_140018864
0x140018825  mov     r9d, [rdi+3Ch]; nInBufferSize
0x140018829  lea     rax, [rsp+48h+BytesReturned]
0x14001882e  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x140018835  mov     r8, rsi; lpInBuffer
0x140018838  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x140018841  mov     edx, 0E7C00Ch; dwIoControlCode
0x140018846  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x14001884b  mov     [rsp+48h+nOutBufferSize], 0; nOutBufferSize
0x140018853  mov     [rsp+48h+lpOutBuffer], 0; lpOutBuffer
0x14001885c  call    cs:__imp_DeviceIoControl
0x140018862  mov     ebx, eax
0x140018864  call    cs:__imp_GetLastError
0x14001886a  mov     esi, eax
0x14001886c  test    rdi, rdi
0x14001886f  jz      short loc_140018890
0x140018871  mov     rcx, rdi; hMem
0x140018874  call    cs:__imp_LocalFree
0x14001887a  xor     ecx, ecx
0x14001887c  test    rax, rax
0x14001887f  setz    cl
0x140018882  test    ebx, ebx
0x140018884  jz      short loc_140018890
0x140018886  mov     ebx, ecx
0x140018888  call    cs:__imp_GetLastError
0x14001888e  mov     esi, eax
0x140018890  mov     ecx, esi; dwErrCode
0x140018892  call    cs:__imp_SetLastError
0x140018898  mov     rsi, [rsp+48h+arg_10]
0x14001889d  mov     eax, ebx
0x14001889f  mov     rbx, [rsp+48h+arg_8]
0x1400188a4  add     rsp, 40h
0x1400188a8  pop     rdi
0x1400188a9  retn
```
