# JobHelper::UpdateBitsJobId(_Job &)

- ea: `0x140019c6c`
- end: `0x140019d5f`
- name: `?UpdateBitsJobId@JobHelper@@SAJAEAU_Job@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(struct _Job *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000d898`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14000740c`
- `0x140018520`
- `0x140019750`
- `0x140019c6c`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140019d0f`
- `KERNEL32!LeaveCriticalSection` at `0x140019d0f`
- `KERNEL32!EnterCriticalSection` at `0x140019ca1`
- `KERNEL32!EnterCriticalSection` at `0x140019ca1`

## string_xrefs

- `0x140019d29`: `UpdateBitsJobId for Job %1. Error = 0x%2!x!.`

## pseudocode

```c
__int64 __fastcall JobHelper::UpdateBitsJobId(struct _Job *a1)
{
  HKEY v2; // rcx
  int JobRegPath; // edi
  const unsigned __int16 *v4; // r9
  const unsigned __int16 *v5; // rdx
  int v6; // eax
  struct _SECURITY_ATTRIBUTES *v8; // [rsp+20h] [rbp-48h]
  int v9; // [rsp+28h] [rbp-40h]
  unsigned __int16 *v10[4]; // [rsp+30h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v10, (__int64)&word_14001E5B4);
  EnterCriticalSection(&JobHelper::m_critSec);
  JobRegPath = JobHelper::GetJobRegPath(a1, (_QWORD *)a1 + 4, v10);
  if ( JobRegPath >= 0 )
  {
    v4 = (const unsigned __int16 *)((char *)a1 + 168);
    if ( *((_QWORD *)a1 + 24) >= 8u )
      v4 = *(const unsigned __int16 **)v4;
    v5 = (const unsigned __int16 *)v10;
    if ( v10[3] >= (unsigned __int16 *)8 )
      v5 = v10[0];
    v6 = WriteRegSZValue(v2, v5, L"BITSJobId", v4, v8, v9);
    JobRegPath = v6;
    if ( v6 < 0 )
      LogError(L"failed to set %1 ,0x%2!x!", L"BITSJobId", (unsigned int)v6);
  }
  LeaveCriticalSection(&JobHelper::m_critSec);
  if ( JobRegPath < 0 )
  {
    if ( *((_QWORD *)a1 + 3) >= 8u )
      a1 = *(struct _Job **)a1;
    LogError(L"UpdateBitsJobId for Job %1. Error = 0x%2!x!.", a1, (unsigned int)JobRegPath);
  }
  std::wstring::_Tidy(v10, 1, 0);
  return (unsigned int)JobRegPath;
}

```

## disassembly

```asm
0x140019c6c  mov     [rsp+arg_8], rbx
0x140019c71  push    rdi
0x140019c72  sub     rsp, 60h
0x140019c76  mov     rax, cs:__security_cookie
0x140019c7d  xor     rax, rsp
0x140019c80  mov     [rsp+68h+var_18], rax
0x140019c85  mov     rbx, rcx
0x140019c88  lea     rdx, word_14001E5B4
0x140019c8f  lea     rcx, [rsp+68h+var_38]
0x140019c94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140019c99  nop
0x140019c9a  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140019ca1  call    cs:__imp_EnterCriticalSection
0x140019ca7  lea     rdx, [rbx+20h]
0x140019cab  lea     r8, [rsp+68h+var_38]
0x140019cb0  mov     rcx, rbx
0x140019cb3  call    ?GetJobRegPath@JobHelper@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV23@@Z; JobHelper::GetJobRegPath(std::wstring const &,std::wstring const &,std::wstring &)
0x140019cb8  mov     edi, eax
0x140019cba  test    eax, eax
0x140019cbc  js      short loc_140019D08
0x140019cbe  lea     r9, [rbx+0A8h]
0x140019cc5  cmp     qword ptr [r9+18h], 8
0x140019cca  jb      short loc_140019CCF
0x140019ccc  mov     r9, [r9]; unsigned __int16 *
0x140019ccf  lea     rdx, [rsp+68h+var_38]
0x140019cd4  cmp     [rsp+68h+var_20], 8
0x140019cda  cmovnb  rdx, [rsp+68h+var_38]; unsigned __int16 *
0x140019ce0  lea     r8, aBitsjobid; "BITSJobId"
0x140019ce7  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x140019cec  mov     edi, eax
0x140019cee  test    eax, eax
0x140019cf0  jns     short loc_140019D08
0x140019cf2  mov     r8d, eax
0x140019cf5  lea     rdx, aBitsjobid; "BITSJobId"
0x140019cfc  lea     rcx, aFailedToSet10x; "failed to set %1 ,0x%2!x!"
0x140019d03  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140019d08  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140019d0f  call    cs:__imp_LeaveCriticalSection
0x140019d15  test    edi, edi
0x140019d17  jns     short loc_140019D36
0x140019d19  cmp     qword ptr [rbx+18h], 8
0x140019d1e  jb      short loc_140019D23
0x140019d20  mov     rbx, [rbx]
0x140019d23  mov     r8d, edi
0x140019d26  mov     rdx, rbx
0x140019d29  lea     rcx, aUpdatebitsjobi; "UpdateBitsJobId for Job %1. Error = 0x%"...
0x140019d30  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140019d35  nop
0x140019d36  xor     r8d, r8d
0x140019d39  mov     dl, 1
0x140019d3b  lea     rcx, [rsp+68h+var_38]
0x140019d40  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140019d45  mov     eax, edi
0x140019d47  mov     rcx, [rsp+68h+var_18]
0x140019d4c  xor     rcx, rsp; StackCookie
0x140019d4f  call    __security_check_cookie
0x140019d54  mov     rbx, [rsp+68h+arg_8]
0x140019d59  add     rsp, 60h
0x140019d5d  pop     rdi
0x140019d5e  retn
```
