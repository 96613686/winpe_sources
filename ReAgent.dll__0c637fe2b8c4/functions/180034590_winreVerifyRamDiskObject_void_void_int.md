# winreVerifyRamDiskObject(void *,void *,int *)

- ea: `0x180034590`
- end: `0x180034796`
- name: `?winreVerifyRamDiskObject@@YAKPEAX0PEAH@Z`
- size: `518`
- prototype: `unsigned int __fastcall(void *, void *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x1800367b8`

## callees

- `0x1800059fc`
- `0x180034590`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180034751`
- `ntdll!RtlNtStatusToDosError` at `0x180034751`
- `KERNEL32!HeapFree` at `0x18003471a`
- `KERNEL32!HeapFree` at `0x18003471a`
- `KERNEL32!HeapAlloc` at `0x180034651`
- `KERNEL32!HeapAlloc` at `0x180034651`
- `KERNEL32!GetProcessHeap` at `0x180034640`
- `KERNEL32!GetProcessHeap` at `0x18003470c`
- `KERNEL32!GetProcessHeap` at `0x180034640`
- `KERNEL32!GetProcessHeap` at `0x18003470c`
- `bcd!BcdGetElementDataWithFlags` at `0x180034609`
- `bcd!BcdGetElementDataWithFlags` at `0x180034609`
- `bcd!BcdCloseObject` at `0x18003472a`
- `bcd!BcdCloseObject` at `0x18003472a`
- `bcd!BcdGetElementData` at `0x1800346a5`
- `bcd!BcdGetElementData` at `0x1800346a5`
- `bcd!BcdOpenObject` at `0x1800346f4`
- `bcd!BcdOpenObject` at `0x1800346f4`

## string_xrefs

- `0x180034700`: `BcdOpenObject failed: 0x%x`
- `0x18003466b`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`

## pseudocode

```c
__int64 __fastcall winreVerifyRamDiskObject(void *a1, void *a2, int *a3)
{
  NTSTATUS ElementDataWithFlags; // edi
  ULONG v7; // esi
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  char *v10; // rax
  char *v11; // rbx
  int ElementData; // eax
  __int64 v13; // rax
  int v14; // eax
  HANDLE v15; // rax
  const wchar_t *v16; // rdx
  __int64 v18; // [rsp+30h] [rbp-58h] BYREF
  SIZE_T dwBytes; // [rsp+38h] [rbp-50h] BYREF

  LODWORD(dwBytes) = 0;
  v18 = 0;
  if ( a3 )
  {
    v7 = 0;
    *a3 = 0;
    ElementDataWithFlags = BcdGetElementDataWithFlags(a2, 285212673, 0, 0, &dwBytes);
    if ( (int)(ElementDataWithFlags + 0x80000000) < 0 || ElementDataWithFlags == -1073741789 )
    {
      v8 = dwBytes;
      ProcessHeap = GetProcessHeap();
      v10 = (char *)HeapAlloc(ProcessHeap, 8u, v8);
      v11 = v10;
      if ( v10 )
      {
        ElementData = BcdGetElementData(a2, 285212673, v10, &dwBytes);
        ElementDataWithFlags = ElementData;
        if ( ElementData >= 0 )
        {
          v13 = *(_QWORD *)&ZeroGuid.Data1 - *(_QWORD *)(v11 + 4);
          if ( *(_QWORD *)&ZeroGuid.Data1 == *(_QWORD *)(v11 + 4) )
            v13 = *(_QWORD *)ZeroGuid.Data4 - *(_QWORD *)(v11 + 12);
          if ( v13 )
          {
            v14 = BcdOpenObject(a1, v11 + 4, &v18);
            ElementDataWithFlags = v14;
            if ( v14 >= 0 )
              *a3 = 1;
            else
              UnattendLogW(1, L"BcdOpenObject failed: 0x%x", (unsigned int)v14);
          }
          else
          {
            v7 = 1168;
          }
        }
        else
        {
          UnattendLogW(1, L"BcdGetElementData failed: 0x%x", (unsigned int)ElementData);
        }
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v11);
      }
      else
      {
        v7 = 8;
        UnattendLogW(2, L"winreVerifyRamDiskObject %s (0x%x) in file %S line %d", L"failed to allocate memory");
      }
    }
    else
    {
      UnattendLogW(1, L"BcdGetElementData failed: 0x%x", (unsigned int)ElementDataWithFlags);
    }
  }
  else
  {
    ElementDataWithFlags = 0;
    UnattendLogW(1, L"NULL parameter");
    v7 = 87;
  }
  if ( v18 )
  {
    BcdCloseObject();
    v18 = 0;
  }
  if ( ElementDataWithFlags < 0 )
  {
    UnattendLogW(1, L"winreVerifyRamDiskObject failed: 0x%x", (unsigned int)ElementDataWithFlags);
    v7 = RtlNtStatusToDosError(ElementDataWithFlags);
  }
  if ( a3 )
  {
    v16 = L"RAM object is in a valid state";
    if ( !*a3 )
      v16 = L" RAM object is not in a valid state";
    UnattendLogW(0, v16);
  }
  return v7;
}

```

## disassembly

```asm
0x180034590  push    rbx
0x180034592  push    rbp
0x180034593  push    rsi
0x180034594  push    rdi
0x180034595  push    r13
0x180034597  push    r14
0x180034599  push    r15
0x18003459b  sub     rsp, 50h
0x18003459f  mov     rax, cs:__security_cookie
0x1800345a6  xor     rax, rsp
0x1800345a9  mov     [rsp+88h+var_48], rax
0x1800345ae  mov     dword ptr [rsp+88h+dwBytes], 0
0x1800345b6  mov     r14, r8
0x1800345b9  mov     [rsp+88h+var_58], 0
0x1800345c2  mov     rbp, rdx
0x1800345c5  mov     r15, rcx
0x1800345c8  mov     r13d, 1
0x1800345ce  test    r8, r8
0x1800345d1  jnz     short loc_1800345EC
0x1800345d3  xor     edi, edi
0x1800345d5  lea     rdx, aNullParameter; "NULL parameter"
0x1800345dc  mov     ecx, r13d
0x1800345df  call    UnattendLogW
0x1800345e4  lea     esi, [rdi+57h]
0x1800345e7  jmp     loc_180034720
0x1800345ec  lea     rax, [rsp+88h+dwBytes]
0x1800345f1  xor     esi, esi
0x1800345f3  mov     [r8], esi
0x1800345f6  xor     r9d, r9d
0x1800345f9  xor     r8d, r8d
0x1800345fc  mov     [rsp+88h+var_68], rax
0x180034601  mov     edx, 11000001h
0x180034606  mov     rcx, rbp
0x180034609  call    cs:__imp_BcdGetElementDataWithFlags
0x18003460f  mov     edi, eax
0x180034611  mov     eax, 80000000h
0x180034616  lea     ecx, [rdi+rax]
0x180034619  test    eax, ecx
0x18003461b  jnz     short loc_18003463C
0x18003461d  cmp     edi, 0C0000023h
0x180034623  jz      short loc_18003463C
0x180034625  mov     r8d, edi
0x180034628  lea     rdx, aBcdgetelementd_2; "BcdGetElementData failed: 0x%x"
0x18003462f  mov     ecx, r13d
0x180034632  call    UnattendLogW
0x180034637  jmp     loc_180034720
0x18003463c  mov     ebx, dword ptr [rsp+88h+dwBytes]
0x180034640  call    cs:__imp_GetProcessHeap
0x180034646  mov     r8d, ebx; dwBytes
0x180034649  mov     edx, 8; dwFlags
0x18003464e  mov     rcx, rax; hHeap
0x180034651  call    cs:__imp_HeapAlloc
0x180034657  mov     rbx, rax
0x18003465a  test    rax, rax
0x18003465d  jnz     short loc_180034695
0x18003465f  lea     r9d, [rax+8]
0x180034663  mov     [rsp+88h+var_60], 77Dh
0x18003466b  lea     rax, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180034672  mov     esi, r9d
0x180034675  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x18003467c  mov     [rsp+88h+var_68], rax
0x180034681  lea     rdx, aWinreverifyram; "winreVerifyRamDiskObject %s (0x%x) in f"...
0x180034688  lea     ecx, [rbx+2]
0x18003468b  call    UnattendLogW
0x180034690  jmp     loc_180034720
0x180034695  lea     r9, [rsp+88h+dwBytes]
0x18003469a  mov     r8, rbx
0x18003469d  mov     edx, 11000001h
0x1800346a2  mov     rcx, rbp
0x1800346a5  call    cs:__imp_BcdGetElementData
0x1800346ab  mov     edi, eax
0x1800346ad  test    eax, eax
0x1800346af  jns     short loc_1800346C5
0x1800346b1  lea     rdx, aBcdgetelementd_2; "BcdGetElementData failed: 0x%x"
0x1800346b8  mov     r8d, eax
0x1800346bb  mov     ecx, r13d
0x1800346be  call    UnattendLogW
0x1800346c3  jmp     short loc_18003470C
0x1800346c5  mov     rax, qword ptr cs:ZeroGuid.Data1
0x1800346cc  lea     rdx, [rbx+4]
0x1800346d0  sub     rax, [rdx]
0x1800346d3  jnz     short loc_1800346E0
0x1800346d5  mov     rax, qword ptr cs:ZeroGuid.Data4
0x1800346dc  sub     rax, [rdx+8]
0x1800346e0  test    rax, rax
0x1800346e3  jnz     short loc_1800346EC
0x1800346e5  mov     esi, 490h
0x1800346ea  jmp     short loc_18003470C
0x1800346ec  lea     r8, [rsp+88h+var_58]
0x1800346f1  mov     rcx, r15
0x1800346f4  call    cs:__imp_BcdOpenObject
0x1800346fa  mov     edi, eax
0x1800346fc  test    eax, eax
0x1800346fe  jns     short loc_180034709
0x180034700  lea     rdx, aBcdopenobjectF_0; "BcdOpenObject failed: 0x%x"
0x180034707  jmp     short loc_1800346B8
0x180034709  mov     [r14], r13d
0x18003470c  call    cs:__imp_GetProcessHeap
0x180034712  mov     r8, rbx; lpMem
0x180034715  xor     edx, edx; dwFlags
0x180034717  mov     rcx, rax; hHeap
0x18003471a  call    cs:__imp_HeapFree
0x180034720  mov     rcx, [rsp+88h+var_58]
0x180034725  test    rcx, rcx
0x180034728  jz      short loc_180034739
0x18003472a  call    cs:__imp_BcdCloseObject
0x180034730  mov     [rsp+88h+var_58], 0
0x180034739  test    edi, edi
0x18003473b  jns     short loc_180034759
0x18003473d  mov     r8d, edi
0x180034740  lea     rdx, aWinreverifyram_0; "winreVerifyRamDiskObject failed: 0x%x"
0x180034747  mov     ecx, r13d
0x18003474a  call    UnattendLogW
0x18003474f  mov     ecx, edi; Status
0x180034751  call    cs:__imp_RtlNtStatusToDosError
0x180034757  mov     esi, eax
0x180034759  test    r14, r14
0x18003475c  jz      short loc_180034778
0x18003475e  xor     ecx, ecx
0x180034760  lea     rdx, aRamObjectIsInA; "RAM object is in a valid state"
0x180034767  cmp     [r14], ecx
0x18003476a  jnz     short loc_180034773
0x18003476c  lea     rdx, aRamObjectIsNot; " RAM object is not in a valid state"
0x180034773  call    UnattendLogW
0x180034778  mov     eax, esi
0x18003477a  mov     rcx, [rsp+88h+var_48]
0x18003477f  xor     rcx, rsp; StackCookie
0x180034782  call    __security_check_cookie
0x180034787  add     rsp, 50h
0x18003478b  pop     r15
0x18003478d  pop     r14
0x18003478f  pop     r13
0x180034791  pop     rdi
0x180034792  pop     rsi
0x180034793  pop     rbp
0x180034794  pop     rbx
0x180034795  retn
```
