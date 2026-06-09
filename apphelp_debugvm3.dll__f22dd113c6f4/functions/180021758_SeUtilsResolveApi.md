# SeUtilsResolveApi

- ea: `0x180021758`
- end: `0x180021980`
- name: `SeUtilsResolveApi`
- size: `552`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001fe10`

## callees

- `0x18000f114`
- `0x180021758`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x1800217cb`
- `ntdll!RtlInitAnsiString` at `0x1800217cb`
- `ntdll!LdrGetProcedureAddressEx` at `0x180021881`
- `ntdll!LdrGetProcedureAddressEx` at `0x180021932`
- `ntdll!LdrGetProcedureAddressEx` at `0x180021881`
- `ntdll!LdrGetProcedureAddressEx` at `0x180021932`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800217f2`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800217f2`
- `ntdll!LdrGetDllHandle` at `0x180021810`
- `ntdll!LdrGetDllHandle` at `0x180021810`
- `ntdll!RtlInitString` at `0x180021861`
- `ntdll!RtlInitString` at `0x180021861`

## pseudocode

```c
__int64 __fastcall SeUtilsResolveApi(PVOID *a1, _QWORD *a2, const char *a3, const char *a4)
{
  NTSTATUS v8; // eax
  NTSTATUS ProcedureAddress; // ebx
  __int64 v11; // rcx
  PVOID DllHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DllName; // [rsp+40h] [rbp-C0h] BYREF
  struct _STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  struct _STRING v16; // [rsp+60h] [rbp-A0h] BYREF
  char v17; // [rsp+70h] [rbp-90h] BYREF

  *a1 = 0;
  *a2 = 0;
  DllHandle = 0;
  v13 = 0;
  DestinationString = 0;
  *(_QWORD *)&DllName.Length = 34078720;
  v16 = 0;
  RtlInitAnsiString(&DestinationString, a3);
  DllName.Buffer = (PWSTR)&v17;
  v8 = RtlAnsiStringToUnicodeString(&DllName, &DestinationString, 0);
  ProcedureAddress = v8;
  if ( v8 < 0 )
  {
    AslLogCallPrintf(1, "SeUtilsResolveApi", 84, "Failed to convert to unicode: %08lx", v8);
    return (unsigned int)ProcedureAddress;
  }
  ProcedureAddress = LdrGetDllHandle(0, 0, &DllName, &DllHandle);
  if ( ProcedureAddress >= 0 )
  {
    if ( DllHandle )
    {
      if ( (unsigned __int64)a4 < 0xFFFF )
      {
        ProcedureAddress = LdrGetProcedureAddressEx(DllHandle, 0, (unsigned int)a4, &v13, 1);
        if ( ProcedureAddress < 0 )
        {
          AslLogCallPrintf(1, "SeUtilsResolveApi", 118, "Failed to get API entry %s!#%d", a3, (_DWORD)a4);
          return (unsigned int)ProcedureAddress;
        }
      }
      else
      {
        RtlInitString(&v16, a4);
        ProcedureAddress = LdrGetProcedureAddressEx(DllHandle, &v16, 0, &v13, 1);
        if ( ProcedureAddress < 0 )
        {
          AslLogCallPrintf(1, "SeUtilsResolveApi", 130, "Failed to get API entry %s!%s", a3, a4);
          return (unsigned int)ProcedureAddress;
        }
      }
      v11 = v13;
      if ( v13 )
      {
        ProcedureAddress = 0;
        *a1 = DllHandle;
        *a2 = v11;
      }
      else
      {
        AslLogCallPrintf(1, "SeUtilsResolveApi", 136, "API not found");
        return (unsigned int)-1073741702;
      }
    }
    else
    {
      ProcedureAddress = -1073741801;
      AslLogCallPrintf(1, "SeUtilsResolveApi", 102, "Got NULL handle for %S", DllName.Buffer);
    }
  }
  return (unsigned int)ProcedureAddress;
}

```

## disassembly

```asm
0x180021758  push    rbp
0x18002175a  push    rbx
0x18002175b  push    rsi
0x18002175c  push    r12
0x18002175e  push    r14
0x180021760  push    r15
0x180021762  lea     rbp, [rsp-198h]
0x18002176a  sub     rsp, 298h
0x180021771  mov     rax, cs:__security_cookie
0x180021778  xor     rax, rsp
0x18002177b  mov     [rbp+1C0h+var_40], rax
0x180021782  mov     qword ptr [rcx], 0
0x180021789  xorps   xmm0, xmm0
0x18002178c  mov     qword ptr [rdx], 0
0x180021793  mov     r12, rdx
0x180021796  mov     r15, rcx
0x180021799  mov     [rsp+2C0h+DllHandle], 0
0x1800217a2  xorps   xmm1, xmm1
0x1800217a5  mov     [rsp+2C0h+var_288], 0
0x1800217ae  mov     rdx, r8; SourceString
0x1800217b1  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x1800217b6  mov     rsi, r9
0x1800217b9  mov     r14, r8
0x1800217bc  movups  xmmword ptr [rsp+2C0h+DestinationString.Length], xmm0
0x1800217c1  movups  xmmword ptr [rsp+2C0h+DllName.Length], xmm1
0x1800217c6  movups  xmmword ptr [rsp+2C0h+var_260.Length], xmm0
0x1800217cb  call    cs:__imp_RtlInitAnsiString
0x1800217d1  mov     eax, 208h
0x1800217d6  lea     rdx, [rsp+2C0h+DestinationString]; SourceString
0x1800217db  mov     [rsp+2C0h+DllName.MaximumLength], ax
0x1800217e0  lea     rcx, [rsp+2C0h+DllName]; DestinationString
0x1800217e5  lea     rax, [rsp+2C0h+var_250]
0x1800217ea  xor     r8d, r8d; AllocateDestinationString
0x1800217ed  mov     [rsp+2C0h+DllName.Buffer], rax
0x1800217f2  call    cs:__imp_RtlAnsiStringToUnicodeString
0x1800217f8  mov     ebx, eax
0x1800217fa  test    eax, eax
0x1800217fc  js      loc_1800218DB
0x180021802  lea     r9, [rsp+2C0h+DllHandle]; DllHandle
0x180021807  xor     edx, edx; DllCharacteristics
0x180021809  lea     r8, [rsp+2C0h+DllName]; DllName
0x18002180e  xor     ecx, ecx; DllPath
0x180021810  call    cs:__imp_LdrGetDllHandle
0x180021816  mov     ebx, eax
0x180021818  test    eax, eax
0x18002181a  jns     short loc_18002183E
0x18002181c  mov     eax, ebx
0x18002181e  mov     rcx, [rbp+1C0h+var_40]
0x180021825  xor     rcx, rsp; StackCookie
0x180021828  call    __security_check_cookie
0x18002182d  add     rsp, 298h
0x180021834  pop     r15
0x180021836  pop     r14
0x180021838  pop     r12
0x18002183a  pop     rsi
0x18002183b  pop     rbx
0x18002183c  pop     rbp
0x18002183d  retn
0x18002183e  mov     rcx, [rsp+2C0h+DllHandle]
0x180021843  test    rcx, rcx
0x180021846  jz      loc_180021902
0x18002184c  cmp     rsi, 0FFFFh
0x180021853  jb      loc_180021920
0x180021859  mov     rdx, rsi; SourceString
0x18002185c  lea     rcx, [rsp+2C0h+var_260]; DestinationString
0x180021861  call    cs:__imp_RtlInitString
0x180021867  mov     rcx, [rsp+2C0h+DllHandle]
0x18002186c  lea     r9, [rsp+2C0h+var_288]
0x180021871  xor     r8d, r8d
0x180021874  mov     dword ptr [rsp+2C0h+var_2A0], 1
0x18002187c  lea     rdx, [rsp+2C0h+var_260]
0x180021881  call    cs:__imp_LdrGetProcedureAddressEx
0x180021887  mov     ebx, eax
0x180021889  test    eax, eax
0x18002188b  js      short loc_1800218AE
0x18002188d  mov     rcx, [rsp+2C0h+var_288]
0x180021892  test    rcx, rcx
0x180021895  jz      loc_180021958
0x18002189b  mov     rax, [rsp+2C0h+DllHandle]
0x1800218a0  xor     ebx, ebx
0x1800218a2  mov     [r15], rax
0x1800218a5  mov     [r12], rcx
0x1800218a9  jmp     loc_18002181C
0x1800218ae  mov     [rsp+2C0h+var_298], rsi
0x1800218b3  lea     r9, aFailedToGetApi; "Failed to get API entry %s!%s"
0x1800218ba  mov     r8d, 82h
0x1800218c0  lea     rdx, aSeutilsresolve; "SeUtilsResolveApi"
0x1800218c7  mov     [rsp+2C0h+var_2A0], r14
0x1800218cc  mov     ecx, 1
0x1800218d1  call    AslLogCallPrintf
0x1800218d6  jmp     loc_18002181C
0x1800218db  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x1800218df  lea     r9, aFailedToConver_1; "Failed to convert to unicode: %08lx"
0x1800218e6  mov     r8d, 54h ; 'T'
0x1800218ec  lea     rdx, aSeutilsresolve; "SeUtilsResolveApi"
0x1800218f3  mov     ecx, 1
0x1800218f8  call    AslLogCallPrintf
0x1800218fd  jmp     loc_18002181C
0x180021902  mov     rax, [rsp+2C0h+DllName.Buffer]
0x180021907  lea     r9, aGotNullHandleF; "Got NULL handle for %S"
0x18002190e  mov     [rsp+2C0h+var_2A0], rax
0x180021913  mov     ebx, 0C0000017h
0x180021918  mov     r8d, 66h ; 'f'
0x18002191e  jmp     short loc_1800218EC
0x180021920  lea     r9, [rsp+2C0h+var_288]
0x180021925  mov     dword ptr [rsp+2C0h+var_2A0], 1
0x18002192d  mov     r8d, esi
0x180021930  xor     edx, edx
0x180021932  call    cs:__imp_LdrGetProcedureAddressEx
0x180021938  mov     ebx, eax
0x18002193a  test    eax, eax
0x18002193c  jns     loc_18002188D
0x180021942  mov     dword ptr [rsp+2C0h+var_298], esi
0x180021946  lea     r9, aFailedToGetApi_0; "Failed to get API entry %s!#%d"
0x18002194d  mov     r8d, 76h ; 'v'
0x180021953  jmp     loc_1800218C0
0x180021958  lea     r9, aApiNotFound; "API not found"
0x18002195f  mov     r8d, 88h
0x180021965  lea     rdx, aSeutilsresolve; "SeUtilsResolveApi"
0x18002196c  mov     ecx, 1
0x180021971  call    AslLogCallPrintf
0x180021976  mov     ebx, 0C000007Ah
0x18002197b  jmp     loc_18002181C
```
