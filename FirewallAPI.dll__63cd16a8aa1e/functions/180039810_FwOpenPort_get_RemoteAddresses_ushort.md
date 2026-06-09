# FwOpenPort::get_RemoteAddresses(ushort * *)

- ea: `0x180039810`
- end: `0x1800398ae`
- name: `?get_RemoteAddresses@FwOpenPort@@UEAAJPEAPEAG@Z`
- size: `158`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180039810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039826`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039826`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039888`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039888`
- `fwbase!FwReportReturnError` at `0x18003987f`
- `fwbase!FwReportReturnError` at `0x18003989b`
- `fwbase!FwReportReturnError` at `0x18003987f`
- `fwbase!FwReportReturnError` at `0x18003989b`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18003986a`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18003986a`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039851`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039851`

## string_xrefs

- `0x180039878`: `FwOpenPort::get_RemoteAddresses`
- `0x180039894`: `FwOpenPort::get_RemoteAddresses`

## pseudocode

```c
__int64 __fastcall FwOpenPort::get_RemoteAddresses(FwOpenPort *this, unsigned __int16 **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int v5; // ebx
  __int64 v6; // rdx
  _QWORD *v7; // rdi
  int OpenPortorAuthAppAsBSTR; // eax

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    v7 = (_QWORD *)((char *)this + 72);
    *a2 = 0;
    if ( *((_QWORD *)this + 9)
      || (OpenPortorAuthAppAsBSTR = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16)),
          v5 = OpenPortorAuthAppAsBSTR,
          OpenPortorAuthAppAsBSTR >= 0) )
    {
      OpenPortorAuthAppAsBSTR = GetOpenPortorAuthAppAsBSTR(*v7 + 176LL, a2);
      v5 = OpenPortorAuthAppAsBSTR;
      if ( OpenPortorAuthAppAsBSTR >= 0 )
        goto LABEL_8;
    }
    v6 = (unsigned int)OpenPortorAuthAppAsBSTR;
  }
  else
  {
    v5 = -2147467261;
    v6 = 2147500035LL;
  }
  FwReportReturnError("FwOpenPort::get_RemoteAddresses", v6);
LABEL_8:
  LeaveCriticalSection(v2);
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::get_RemoteAddresses", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180039810  push    rbx
0x180039812  push    rbp
0x180039813  push    rsi
0x180039814  push    rdi
0x180039815  sub     rsp, 28h
0x180039819  lea     rbp, [rcx+10h]
0x18003981d  mov     rbx, rcx
0x180039820  mov     rcx, rbp; lpCriticalSection
0x180039823  mov     rsi, rdx
0x180039826  call    cs:__imp_EnterCriticalSection
0x18003982c  test    rsi, rsi
0x18003982f  jnz     short loc_18003983A
0x180039831  mov     ebx, 80004003h
0x180039836  mov     edx, ebx
0x180039838  jmp     short loc_180039878
0x18003983a  lea     rdi, [rbx+48h]
0x18003983e  mov     qword ptr [rsi], 0
0x180039845  cmp     qword ptr [rdi], 0
0x180039849  jnz     short loc_18003985D
0x18003984b  mov     edx, [rbx+40h]
0x18003984e  mov     rcx, rdi
0x180039851  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x180039857  mov     ebx, eax
0x180039859  test    eax, eax
0x18003985b  js      short loc_180039876
0x18003985d  mov     rcx, [rdi]
0x180039860  mov     rdx, rsi
0x180039863  add     rcx, 0B0h
0x18003986a  call    cs:__imp_GetOpenPortorAuthAppAsBSTR
0x180039870  mov     ebx, eax
0x180039872  test    eax, eax
0x180039874  jns     short loc_180039885
0x180039876  mov     edx, eax
0x180039878  lea     rcx, aFwopenportGetR; "FwOpenPort::get_RemoteAddresses"
0x18003987f  call    cs:__imp_FwReportReturnError
0x180039885  mov     rcx, rbp; lpCriticalSection
0x180039888  call    cs:__imp_LeaveCriticalSection
0x18003988e  test    ebx, ebx
0x180039890  jns     short loc_1800398A3
0x180039892  mov     edx, ebx
0x180039894  lea     rcx, aFwopenportGetR; "FwOpenPort::get_RemoteAddresses"
0x18003989b  call    cs:__imp_FwReportReturnError
0x1800398a1  mov     ebx, eax
0x1800398a3  mov     eax, ebx
0x1800398a5  add     rsp, 28h
0x1800398a9  pop     rdi
0x1800398aa  pop     rsi
0x1800398ab  pop     rbp
0x1800398ac  pop     rbx
0x1800398ad  retn
```
