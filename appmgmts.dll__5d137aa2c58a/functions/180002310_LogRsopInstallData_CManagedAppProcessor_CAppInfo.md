# LogRsopInstallData(CManagedAppProcessor *,CAppInfo *)

- ea: `0x180002310`
- end: `0x180002393`
- name: `?LogRsopInstallData@@YAXPEAVCManagedAppProcessor@@PEAVCAppInfo@@@Z`
- size: `131`
- prototype: `void __fastcall(HKEY *, struct CAppInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180003370`
- `0x180004780`

## callees

- `0x180002310`
- `0x18000b16c`
- `0x18000b648`
- `0x180011f28`
- `0x1800295b4`

## import_xrefs

- `USERENV!LeaveCriticalPolicySection` at `0x180002379`
- `USERENV!LeaveCriticalPolicySection` at `0x180002379`

## pseudocode

```c
void __fastcall LogRsopInstallData(HKEY *a1, struct CAppInfo *a2)
{
  CRsopAppContext *v2; // rsi
  HKEY v5; // rcx

  v2 = (CRsopAppContext *)(a1 + 45);
  if ( *((_DWORD *)a1 + 98) && (int)CRsopContext::GetExclusiveLoggingAccess((CRsopContext *)(a1 + 45), a1[33] == 0) >= 0 )
  {
    CAppList::WriteAppToRsopLog((CAppList *)(a1 + 4), a2);
    CAppList::WriteLog((CAppList *)(a1 + 4), 1u);
    CRsopAppContext::WriteCurrentRsopVersion(v2, a1[36]);
    v5 = a1[53];
    if ( v5 )
    {
      LeaveCriticalPolicySection(v5);
      a1[53] = 0;
    }
  }
}

```

## disassembly

```asm
0x180002310  push    rbx
0x180002312  push    rbp
0x180002313  push    rsi
0x180002314  push    rdi
0x180002315  sub     rsp, 28h
0x180002319  lea     rsi, [rcx+168h]
0x180002320  mov     rbp, rdx
0x180002323  cmp     dword ptr [rsi+20h], 0
0x180002327  mov     rdi, rcx
0x18000232a  jz      short loc_18000238A
0x18000232c  xor     edx, edx
0x18000232e  cmp     [rcx+108h], rdx
0x180002335  mov     rcx, rsi; this
0x180002338  setz    dl; int
0x18000233b  call    ?GetExclusiveLoggingAccess@CRsopContext@@QEAAJH@Z; CRsopContext::GetExclusiveLoggingAccess(int)
0x180002340  test    eax, eax
0x180002342  js      short loc_18000238A
0x180002344  mov     rdx, rbp; struct CAppInfo *
0x180002347  lea     rcx, [rdi+20h]; this
0x18000234b  call    ?WriteAppToRsopLog@CAppList@@QEAAJPEAVCAppInfo@@@Z; CAppList::WriteAppToRsopLog(CAppInfo *)
0x180002350  mov     edx, 1; unsigned int
0x180002355  lea     rcx, [rdi+20h]; this
0x180002359  call    ?WriteLog@CAppList@@QEAAJK@Z; CAppList::WriteLog(ulong)
0x18000235e  mov     rdx, [rdi+120h]; HKEY
0x180002365  mov     rcx, rsi; this
0x180002368  call    ?WriteCurrentRsopVersion@CRsopAppContext@@QEAAKPEAUHKEY__@@@Z; CRsopAppContext::WriteCurrentRsopVersion(HKEY__ *)
0x18000236d  mov     rcx, [rdi+1A8h]; hSection
0x180002374  test    rcx, rcx
0x180002377  jz      short loc_18000238A
0x180002379  call    cs:__imp_LeaveCriticalPolicySection
0x18000237f  mov     qword ptr [rdi+1A8h], 0
0x18000238a  add     rsp, 28h
0x18000238e  pop     rdi
0x18000238f  pop     rsi
0x180002390  pop     rbp
0x180002391  pop     rbx
0x180002392  retn
```
