# OrchestrateUpdateImageState(HKEY__ *,HKEY__ *,ushort const *)

- ea: `0x1800488e0`
- end: `0x180048a66`
- name: `?OrchestrateUpdateImageState@@YAJPEAUHKEY__@@0PEBG@Z`
- size: `390`
- prototype: `__int64 __fastcall(HKEY, HKEY, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024320`
- `0x180028f50`
- `0x180048210`
- `0x180048320`

## callees

- `0x180047bd0`
- `0x1800481c8`
- `0x180048650`
- `0x1800488e0`
- `0x180048a6c`
- `0x180048b64`
- `0x18004a728`
- `0x18004a7ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048a40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048a40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048a4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180048a4e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180048a12`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180048a12`

## string_xrefs

- `0x180048a20`: `OrchestrateUpdateImageState: Updating image state from [%s] --> [%s]`
- `0x1800489aa`: `IMAGE_STATE_COMPLETE`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall OrchestrateUpdateImageState(HKEY a1, HKEY a2, const unsigned __int16 *a3)
{
  const WCHAR *lpString2; // rbx
  int CurrentGeneralizationState; // esi
  __int64 v5; // rcx
  BOOL v6; // edi
  const wchar_t *v7; // rdx
  const wchar_t *v8; // rax
  int ImageState; // eax
  WCHAR *v10; // rdi
  unsigned int v11; // esi
  const wchar_t *v12; // rdx
  __int64 v13; // rcx
  HANDLE ProcessHeap; // rax
  PCNZWCH lpString1; // [rsp+48h] [rbp+10h] BYREF
  const unsigned __int16 *v17; // [rsp+50h] [rbp+18h] BYREF

  v17 = a3;
  lpString1 = 0;
  lpString2 = L"IMAGE_STATE_UNDEPLOYABLE";
  CurrentGeneralizationState = SysprepGetCurrentGeneralizationStateEx(a1);
  v6 = (unsigned int)RegExists(-2147483646, L"System\\Setup\\Status", L"AuditBoot")
    && (unsigned int)RegGetDword(-2147483646, L"System\\Setup\\Status", L"AuditBoot");
  LODWORD(v17) = 0;
  if ( CurrentGeneralizationState == 4 )
  {
    if ( (int)OrchestrateGetCompletionStatusEx(v5, L"setup.exe", &v17) < 0 || (_DWORD)v17 )
      goto LABEL_19;
    lpString2 = L"IMAGE_STATE_GENERALIZE_RESEAL_TO_AUDIT";
    v8 = L"IMAGE_STATE_GENERALIZE_RESEAL_TO_OOBE";
    goto LABEL_17;
  }
  if ( CurrentGeneralizationState == 7 )
  {
    v7 = L"audit.exe";
    if ( !v6 )
      v7 = L"oobeldr.exe";
    if ( (int)OrchestrateGetCompletionStatusEx(v5, v7, &v17) >= 0 )
    {
      if ( (_DWORD)v17 )
      {
        if ( (_DWORD)v17 != 3 )
          goto LABEL_19;
        lpString2 = L"IMAGE_STATE_SPECIALIZE_RESEAL_TO_AUDIT";
        v8 = L"IMAGE_STATE_COMPLETE";
      }
      else
      {
        v8 = L"IMAGE_STATE_SPECIALIZE_RESEAL_TO_OOBE";
        lpString2 = L"IMAGE_STATE_SPECIALIZE_RESEAL_TO_AUDIT";
      }
LABEL_17:
      if ( !v6 )
        lpString2 = v8;
    }
  }
LABEL_19:
  ImageState = OrchestrateGetImageState(v5, &lpString1);
  v10 = (WCHAR *)lpString1;
  v11 = ImageState;
  if ( ImageState >= 0 )
  {
    if ( CompareStringW(0x409u, 1u, lpString1, -1, lpString2, -1) != 2 )
      UnattendLogW(0, L"OrchestrateUpdateImageState: Updating image state from [%s] --> [%s]", v10, lpString2);
    v11 = OrchestrateSetImageState(v13, v12, lpString2);
  }
  if ( v10 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  return v11;
}

```

## disassembly

```asm
0x1800488e0  mov     rax, rsp
0x1800488e3  mov     [rax+8], rbx
0x1800488e7  mov     [rax+20h], rsi
0x1800488eb  mov     [rax+18h], r8
0x1800488ef  mov     [rax+10h], rdx
0x1800488f3  push    rdi
0x1800488f4  sub     rsp, 30h
0x1800488f8  mov     qword ptr [rax+10h], 0
0x180048900  lea     rbx, aImageStateUnde; "IMAGE_STATE_UNDEPLOYABLE"
0x180048907  call    SysprepGetCurrentGeneralizationStateEx
0x18004890c  mov     rdi, 0FFFFFFFF80000002h
0x180048913  lea     r8, aAuditboot; "AuditBoot"
0x18004891a  mov     rcx, rdi
0x18004891d  lea     rdx, aSystemSetupSta; "System\\Setup\\Status"
0x180048924  mov     esi, eax
0x180048926  call    RegExists
0x18004892b  test    eax, eax
0x18004892d  jz      short loc_180048950
0x18004892f  lea     r8, aAuditboot; "AuditBoot"
0x180048936  mov     rcx, rdi
0x180048939  lea     rdx, aSystemSetupSta; "System\\Setup\\Status"
0x180048940  call    RegGetDword
0x180048945  test    eax, eax
0x180048947  jz      short loc_180048950
0x180048949  mov     edi, 1
0x18004894e  jmp     short loc_180048952
0x180048950  xor     edi, edi
0x180048952  mov     dword ptr [rsp+38h+arg_10], 0
0x18004895a  cmp     esi, 4
0x18004895d  jz      short loc_1800489B3
0x18004895f  cmp     esi, 7
0x180048962  jnz     short loc_1800489E3
0x180048964  lea     rax, aOobeldrExe; "oobeldr.exe"
0x18004896b  test    edi, edi
0x18004896d  lea     rdx, aAuditExe; "audit.exe"
0x180048974  cmovz   rdx, rax
0x180048978  lea     r8, [rsp+38h+arg_10]
0x18004897d  call    OrchestrateGetCompletionStatusEx
0x180048982  test    eax, eax
0x180048984  js      short loc_1800489E3
0x180048986  mov     eax, dword ptr [rsp+38h+arg_10]
0x18004898a  test    eax, eax
0x18004898c  jnz     short loc_18004899E
0x18004898e  lea     rax, aImageStateSpec; "IMAGE_STATE_SPECIALIZE_RESEAL_TO_OOBE"
0x180048995  lea     rbx, aImageStateSpec_0; "IMAGE_STATE_SPECIALIZE_RESEAL_TO_AUDIT"
0x18004899c  jmp     short loc_1800489DD
0x18004899e  cmp     eax, 3
0x1800489a1  jnz     short loc_1800489E3
0x1800489a3  lea     rbx, aImageStateSpec_0; "IMAGE_STATE_SPECIALIZE_RESEAL_TO_AUDIT"
0x1800489aa  lea     rax, aImageStateComp; "IMAGE_STATE_COMPLETE"
0x1800489b1  jmp     short loc_1800489DD
0x1800489b3  lea     r8, [rsp+38h+arg_10]
0x1800489b8  lea     rdx, aSetupExe; "setup.exe"
0x1800489bf  call    OrchestrateGetCompletionStatusEx
0x1800489c4  test    eax, eax
0x1800489c6  js      short loc_1800489E3
0x1800489c8  cmp     dword ptr [rsp+38h+arg_10], 0
0x1800489cd  jnz     short loc_1800489E3
0x1800489cf  lea     rbx, aImageStateGene_0; "IMAGE_STATE_GENERALIZE_RESEAL_TO_AUDIT"
0x1800489d6  lea     rax, aImageStateGene; "IMAGE_STATE_GENERALIZE_RESEAL_TO_OOBE"
0x1800489dd  test    edi, edi
0x1800489df  cmovz   rbx, rax
0x1800489e3  lea     rdx, [rsp+38h+lpString1]
0x1800489e8  call    OrchestrateGetImageState
0x1800489ed  mov     rdi, [rsp+38h+lpString1]
0x1800489f2  mov     esi, eax
0x1800489f4  test    eax, eax
0x1800489f6  js      short loc_180048A3B
0x1800489f8  or      r9d, 0FFFFFFFFh; cchCount1
0x1800489fc  mov     r8, rdi; lpString1
0x1800489ff  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180048a04  mov     ecx, 409h; Locale
0x180048a09  mov     [rsp+38h+lpString2], rbx; lpString2
0x180048a0e  lea     edx, [r9+2]; dwCmpFlags
0x180048a12  call    cs:__imp_CompareStringW
0x180048a18  cmp     eax, 2
0x180048a1b  jz      short loc_180048A31
0x180048a1d  mov     r9, rbx
0x180048a20  lea     rdx, aOrchestrateupd; "OrchestrateUpdateImageState: Updating i"...
0x180048a27  mov     r8, rdi
0x180048a2a  xor     ecx, ecx
0x180048a2c  call    UnattendLogW
0x180048a31  mov     r8, rbx
0x180048a34  call    OrchestrateSetImageState
0x180048a39  mov     esi, eax
0x180048a3b  test    rdi, rdi
0x180048a3e  jz      short loc_180048A54
0x180048a40  call    cs:__imp_GetProcessHeap
0x180048a46  mov     r8, rdi; lpMem
0x180048a49  xor     edx, edx; dwFlags
0x180048a4b  mov     rcx, rax; hHeap
0x180048a4e  call    cs:__imp_HeapFree
0x180048a54  mov     rbx, [rsp+38h+arg_0]
0x180048a59  mov     eax, esi
0x180048a5b  mov     rsi, [rsp+38h+arg_18]
0x180048a60  add     rsp, 30h
0x180048a64  pop     rdi
0x180048a65  retn
```
