# FveDomain::GetDomainInfo(bool *,_GUID *)

- ea: `0x180020430`
- end: `0x180020577`
- name: `?GetDomainInfo@FveDomain@@SAJPEA_NPEAU_GUID@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(bool *, struct _GUID *)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020084`
- `0x1800317b0`
- `0x18003afc8`
- `0x18003b560`
- `0x18004aaec`
- `0x180052594`
- `0x180060254`
- `0x180078390`

## callees

- `0x180009f60`
- `0x18001b890`
- `0x180020430`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002048d`
- `ntdll!RtlNtStatusToDosError` at `0x18002048d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002055b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002055b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180020546`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180020546`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002047b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002047b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800204ec`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800204ec`

## pseudocode

```c
__int64 __fastcall FveDomain::GetDomainInfo(bool *a1, struct _GUID *a2)
{
  int v4; // eax
  signed int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  struct _GUID *v9; // rcx
  NTSTATUS v10; // eax
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+80h] [rbp+30h] BYREF
  PVOID PolicyHandle; // [rsp+88h] [rbp+38h] BYREF

  PolicyHandle = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ObjectAttributes.Length = 48;
  v4 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v4 < 0 )
  {
    v5 = RtlNtStatusToDosError(v4);
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_8;
    v8 = 10;
    goto LABEL_7;
  }
  v10 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
  if ( v10 < 0 )
  {
    v6 = FromNtStatus(v10);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_8;
    v8 = 11;
LABEL_7:
    WPP_SF_d(v7[2], v8, WPP_251a3021e63d3c6493de6f296bf5551c_Traceguids, v6);
LABEL_8:
    v9 = (struct _GUID *)Buffer;
    goto LABEL_15;
  }
  v9 = (struct _GUID *)Buffer;
  v6 = 0;
  *a1 = *((_QWORD *)Buffer + 8) != 0;
  if ( a2 )
    *a2 = v9[3];
LABEL_15:
  if ( v9 )
    LsaFreeMemory(v9);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v6;
}

```

## disassembly

```asm
0x180020430  mov     [rsp-18h+arg_0], rbx
0x180020435  push    rbp
0x180020436  push    rsi
0x180020437  push    rdi
0x180020438  mov     rbp, rsp
0x18002043b  sub     rsp, 50h
0x18002043f  xorps   xmm0, xmm0
0x180020442  mov     [rbp+PolicyHandle], 0
0x18002044a  mov     rdi, rdx
0x18002044d  mov     [rbp+Buffer], 0
0x180020455  mov     rsi, rcx
0x180020458  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18002045c  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180020460  mov     r8d, 1; DesiredAccess
0x180020466  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002046d  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x180020471  xor     ecx, ecx; SystemName
0x180020473  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180020477  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002047b  call    cs:__imp_LsaOpenPolicy
0x180020482  nop     dword ptr [rax+rax+00h]
0x180020487  test    eax, eax
0x180020489  jns     short loc_1800204DF
0x18002048b  mov     ecx, eax; Status
0x18002048d  call    cs:__imp_RtlNtStatusToDosError
0x180020494  nop     dword ptr [rax+rax+00h]
0x180020499  mov     ebx, eax
0x18002049b  test    eax, eax
0x18002049d  jle     short loc_1800204A8
0x18002049f  movzx   ebx, ax
0x1800204a2  or      ebx, 80070000h
0x1800204a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204af  lea     rax, WPP_GLOBAL_Control
0x1800204b6  cmp     rcx, rax
0x1800204b9  jz      short loc_1800204D9
0x1800204bb  test    byte ptr [rcx+1Ch], 40h
0x1800204bf  jz      short loc_1800204D9
0x1800204c1  mov     edx, 0Ah
0x1800204c6  mov     rcx, [rcx+10h]
0x1800204ca  lea     r8, WPP_251a3021e63d3c6493de6f296bf5551c_Traceguids
0x1800204d1  mov     r9d, ebx
0x1800204d4  call    WPP_SF_d
0x1800204d9  mov     rcx, [rbp+Buffer]
0x1800204dd  jmp     short loc_180020541
0x1800204df  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800204e3  lea     r8, [rbp+Buffer]; Buffer
0x1800204e7  mov     edx, 0Ch; InformationClass
0x1800204ec  call    cs:__imp_LsaQueryInformationPolicy
0x1800204f3  nop     dword ptr [rax+rax+00h]
0x1800204f8  test    eax, eax
0x1800204fa  jns     short loc_180020525
0x1800204fc  mov     ecx, eax; int
0x1800204fe  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180020503  mov     ebx, eax
0x180020505  mov     rcx, cs:WPP_GLOBAL_Control
0x18002050c  lea     rax, WPP_GLOBAL_Control
0x180020513  cmp     rcx, rax
0x180020516  jz      short loc_1800204D9
0x180020518  test    byte ptr [rcx+1Ch], 40h
0x18002051c  jz      short loc_1800204D9
0x18002051e  mov     edx, 0Bh
0x180020523  jmp     short loc_1800204C6
0x180020525  mov     rcx, [rbp+Buffer]; Buffer
0x180020529  xor     ebx, ebx
0x18002052b  cmp     [rcx+40h], rbx
0x18002052f  setnz   al
0x180020532  mov     [rsi], al
0x180020534  test    rdi, rdi
0x180020537  jz      short loc_180020541
0x180020539  movups  xmm0, xmmword ptr [rcx+30h]
0x18002053d  movdqu  xmmword ptr [rdi], xmm0
0x180020541  test    rcx, rcx
0x180020544  jz      short loc_180020552
0x180020546  call    cs:__imp_LsaFreeMemory
0x18002054d  nop     dword ptr [rax+rax+00h]
0x180020552  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180020556  test    rcx, rcx
0x180020559  jz      short loc_180020567
0x18002055b  call    cs:__imp_LsaClose
0x180020562  nop     dword ptr [rax+rax+00h]
0x180020567  mov     eax, ebx
0x180020569  mov     rbx, [rsp+50h+arg_0]
0x18002056e  add     rsp, 50h
0x180020572  pop     rdi
0x180020573  pop     rsi
0x180020574  pop     rbp
0x180020575  retn
```
