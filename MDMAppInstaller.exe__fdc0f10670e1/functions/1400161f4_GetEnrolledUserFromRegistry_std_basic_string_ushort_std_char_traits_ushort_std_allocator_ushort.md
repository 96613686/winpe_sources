# GetEnrolledUserFromRegistry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1400161f4`
- end: `0x1400162c4`
- name: `?GetEnrolledUserFromRegistry@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400165f8`

## callees

- `0x140006604`
- `0x1400068c8`
- `0x14000740c`
- `0x1400074d4`
- `0x14000775c`
- `0x1400161f4`
- `0x140017fbc`
- `0x14001a8aa`
- `0x14001a8d0`

## string_xrefs

- `0x140016252`: `Unable to read the MDM enrolled User SID from the registry. Error = 0x%1!x!`
- `0x140016260`: `GetEnrolledUserFromRegistry() failed hr=0x%1!x!`
- `0x140016295`: `GetEnrolledUserFromRegistry found user %1.`
- `0x140016228`: `EnrolledUserSID`

## pseudocode

```c
__int64 __fastcall GetEnrolledUserFromRegistry(_QWORD *a1)
{
  HKEY v2; // r8
  int RegSZValue; // eax
  unsigned int v4; // edi
  __int64 v5; // rax
  unsigned int *v7; // [rsp+28h] [rbp-230h]
  BYTE Data[528]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Data, 0, 0x20Au);
  RegSZValue = ReadRegSZValue(
                 Data,
                 0x105u,
                 v2,
                 L"SOFTWARE\\Microsoft\\EnterpriseDesktopAppManagement",
                 L"EnrolledUserSID",
                 v7);
  v4 = RegSZValue;
  if ( RegSZValue >= 0 )
  {
    v5 = std::char_traits<unsigned short>::length(Data);
    std::wstring::assign(a1, (unsigned __int64)Data, v5);
    if ( a1[3] >= 8u )
      a1 = (_QWORD *)*a1;
    LogInfo(L"GetEnrolledUserFromRegistry found user %1.", a1);
  }
  else
  {
    LogWarn(L"Unable to read the MDM enrolled User SID from the registry. Error = 0x%1!x!", (unsigned int)RegSZValue);
    LogError(L"GetEnrolledUserFromRegistry() failed hr=0x%1!x!", v4);
  }
  return v4;
}

```

## disassembly

```asm
0x1400161f4  mov     [rsp+arg_8], rbx
0x1400161f9  push    rdi
0x1400161fa  sub     rsp, 250h
0x140016201  mov     rax, cs:__security_cookie
0x140016208  xor     rax, rsp
0x14001620b  mov     [rsp+258h+var_18], rax
0x140016213  mov     rbx, rcx
0x140016216  xor     edx, edx; Val
0x140016218  lea     rcx, [rsp+258h+Data]; void *
0x14001621d  mov     r8d, 20Ah; Size
0x140016223  call    memset_0
0x140016228  lea     rax, aEnrolledusersi; "EnrolledUserSID"
0x14001622f  mov     edx, 105h; unsigned __int64
0x140016234  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\EnterpriseDesktopA"...
0x14001623b  mov     [rsp+258h+var_238], rax; unsigned __int16 *
0x140016240  lea     rcx, [rsp+258h+Data]; lpData
0x140016245  call    ?ReadRegSZValue@@YAJPEAG_KPEAUHKEY__@@PEBG3PEAK@Z; ReadRegSZValue(ushort *,unsigned __int64,HKEY__ *,ushort const *,ushort const *,ulong *)
0x14001624a  mov     edi, eax
0x14001624c  test    eax, eax
0x14001624e  jns     short loc_14001626E
0x140016250  mov     edx, eax
0x140016252  lea     rcx, aUnableToReadTh; "Unable to read the MDM enrolled User SI"...
0x140016259  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x14001625e  mov     edx, edi
0x140016260  lea     rcx, aGetenrolleduse_0; "GetEnrolledUserFromRegistry() failed hr"...
0x140016267  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001626c  jmp     short loc_1400162A1
0x14001626e  lea     rcx, [rsp+258h+Data]
0x140016273  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140016278  mov     r8, rax
0x14001627b  lea     rdx, [rsp+258h+Data]
0x140016280  mov     rcx, rbx
0x140016283  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140016288  cmp     qword ptr [rbx+18h], 8
0x14001628d  jb      short loc_140016292
0x14001628f  mov     rbx, [rbx]
0x140016292  mov     rdx, rbx
0x140016295  lea     rcx, aGetenrolleduse; "GetEnrolledUserFromRegistry found user "...
0x14001629c  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x1400162a1  mov     eax, edi
0x1400162a3  mov     rcx, [rsp+258h+var_18]
0x1400162ab  xor     rcx, rsp; StackCookie
0x1400162ae  call    __security_check_cookie
0x1400162b3  mov     rbx, [rsp+258h+arg_8]
0x1400162bb  add     rsp, 250h
0x1400162c2  pop     rdi
0x1400162c3  retn
```
