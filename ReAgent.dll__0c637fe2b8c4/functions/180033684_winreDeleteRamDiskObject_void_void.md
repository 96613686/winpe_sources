# winreDeleteRamDiskObject(void *,void *)

- ea: `0x180033684`
- end: `0x18003385c`
- name: `?winreDeleteRamDiskObject@@YAKPEAX0@Z`
- size: `472`
- prototype: `unsigned int __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x1800357cc`

## callees

- `0x1800059fc`
- `0x180033684`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180033831`
- `ntdll!RtlNtStatusToDosError` at `0x180033831`
- `KERNEL32!HeapFree` at `0x1800337fa`
- `KERNEL32!HeapFree` at `0x1800337fa`
- `KERNEL32!HeapAlloc` at `0x180033716`
- `KERNEL32!HeapAlloc` at `0x180033716`
- `KERNEL32!GetProcessHeap` at `0x180033705`
- `KERNEL32!GetProcessHeap` at `0x1800337ec`
- `KERNEL32!GetProcessHeap` at `0x180033705`
- `KERNEL32!GetProcessHeap` at `0x1800337ec`
- `bcd!BcdDeleteObject` at `0x1800337d2`
- `bcd!BcdDeleteObject` at `0x1800337d2`
- `bcd!BcdGetElementDataWithFlags` at `0x1800336cb`
- `bcd!BcdGetElementDataWithFlags` at `0x1800336cb`
- `bcd!BcdCloseObject` at `0x18003380a`
- `bcd!BcdCloseObject` at `0x18003380a`
- `bcd!BcdGetElementData` at `0x180033769`
- `bcd!BcdGetElementData` at `0x180033769`
- `bcd!BcdOpenObject` at `0x1800337b8`
- `bcd!BcdOpenObject` at `0x1800337b8`

## string_xrefs

- `0x1800337c4`: `BcdOpenObject failed: 0x%x`
- `0x18003372f`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180033745`: `winreDeleteRamDiskObject %s (0x%x) in file %S line %d`
- `0x1800337de`: `BcdDeleteObject filed: 0x%x`
- `0x180033820`: `winreDeleteRamDiskObject failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreDeleteRamDiskObject(void *a1, void *a2)
{
  unsigned int v4; // esi
  NTSTATUS ElementDataWithFlags; // edi
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rax
  char *v8; // rax
  char *v9; // rbx
  int ElementData; // eax
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  HANDLE v14; // rax
  __int64 v16; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T dwBytes; // [rsp+38h] [rbp-40h] BYREF

  v4 = 0;
  v16 = 0;
  LODWORD(dwBytes) = 0;
  ElementDataWithFlags = BcdGetElementDataWithFlags(a2, 285212673, 0, 0, &dwBytes);
  if ( (int)(ElementDataWithFlags + 0x80000000) < 0 || ElementDataWithFlags == -1073741789 )
  {
    v6 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v8 = (char *)HeapAlloc(ProcessHeap, 8u, v6);
    v9 = v8;
    if ( v8 )
    {
      ElementData = BcdGetElementData(a2, 285212673, v8, &dwBytes);
      ElementDataWithFlags = ElementData;
      if ( ElementData >= 0 )
      {
        v11 = *(_QWORD *)&ZeroGuid.Data1 - *(_QWORD *)(v9 + 4);
        if ( *(_QWORD *)&ZeroGuid.Data1 == *(_QWORD *)(v9 + 4) )
          v11 = *(_QWORD *)ZeroGuid.Data4 - *(_QWORD *)(v9 + 12);
        if ( v11 )
        {
          v12 = BcdOpenObject(a1, v9 + 4, &v16);
          ElementDataWithFlags = v12;
          if ( v12 >= 0 )
          {
            v13 = BcdDeleteObject(v16);
            ElementDataWithFlags = v13;
            if ( v13 >= 0 )
              v16 = 0;
            else
              UnattendLogW(1, L"BcdDeleteObject filed: 0x%x", (unsigned int)v13);
          }
          else
          {
            UnattendLogW(1, L"BcdOpenObject failed: 0x%x", (unsigned int)v12);
          }
        }
        else
        {
          v4 = 1168;
        }
      }
      else
      {
        UnattendLogW(1, L"BcdGetElementData failed: 0x%x", (unsigned int)ElementData);
      }
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v9);
    }
    else
    {
      v4 = 8;
      UnattendLogW(
        2,
        L"winreDeleteRamDiskObject %s (0x%x) in file %S line %d",
        L"failed to allocate memory",
        8,
        "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
        1598);
    }
  }
  else
  {
    UnattendLogW(1, L"BcdGetElementData failed: 0x%x", (unsigned int)ElementDataWithFlags);
  }
  if ( v16 )
  {
    BcdCloseObject();
    v16 = 0;
  }
  if ( ElementDataWithFlags < 0 )
  {
    UnattendLogW(1, L"winreDeleteRamDiskObject failed: 0x%x", (unsigned int)ElementDataWithFlags);
    return RtlNtStatusToDosError(ElementDataWithFlags);
  }
  return v4;
}

```

## disassembly

```asm
0x180033684  mov     r11, rsp
0x180033687  mov     [r11+18h], rbx
0x18003368b  push    rbp
0x18003368c  push    rsi
0x18003368d  push    rdi
0x18003368e  push    r12
0x180033690  push    r14
0x180033692  sub     rsp, 50h
0x180033696  mov     rax, cs:__security_cookie
0x18003369d  xor     rax, rsp
0x1800336a0  mov     [rsp+78h+var_38], rax
0x1800336a5  mov     rbp, rdx
0x1800336a8  lea     rax, [r11-40h]
0x1800336ac  mov     r14, rcx
0x1800336af  mov     [r11-58h], rax
0x1800336b3  xor     esi, esi
0x1800336b5  mov     rcx, rbp
0x1800336b8  xor     r9d, r9d
0x1800336bb  mov     [r11-48h], rsi
0x1800336bf  xor     r8d, r8d
0x1800336c2  mov     dword ptr [rsp+78h+dwBytes], esi
0x1800336c6  mov     edx, 11000001h
0x1800336cb  call    cs:__imp_BcdGetElementDataWithFlags
0x1800336d1  mov     ecx, 80000000h
0x1800336d6  lea     r12d, [rsi+1]
0x1800336da  mov     edi, eax
0x1800336dc  add     eax, ecx
0x1800336de  test    ecx, eax
0x1800336e0  jnz     short loc_180033701
0x1800336e2  cmp     edi, 0C0000023h
0x1800336e8  jz      short loc_180033701
0x1800336ea  mov     r8d, edi
0x1800336ed  lea     rdx, aBcdgetelementd_2; "BcdGetElementData failed: 0x%x"
0x1800336f4  mov     ecx, r12d
0x1800336f7  call    UnattendLogW
0x1800336fc  jmp     loc_180033800
0x180033701  mov     ebx, dword ptr [rsp+78h+dwBytes]
0x180033705  call    cs:__imp_GetProcessHeap
0x18003370b  mov     r8d, ebx; dwBytes
0x18003370e  mov     edx, 8; dwFlags
0x180033713  mov     rcx, rax; hHeap
0x180033716  call    cs:__imp_HeapAlloc
0x18003371c  mov     rbx, rax
0x18003371f  test    rax, rax
0x180033722  jnz     short loc_180033759
0x180033724  lea     esi, [rax+8]
0x180033727  mov     [rsp+78h+var_50], 63Eh
0x18003372f  lea     rax, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180033736  mov     r9d, esi
0x180033739  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x180033740  mov     [rsp+78h+var_58], rax
0x180033745  lea     rdx, aWinredeleteram; "winreDeleteRamDiskObject %s (0x%x) in f"...
0x18003374c  lea     ecx, [rbx+2]
0x18003374f  call    UnattendLogW
0x180033754  jmp     loc_180033800
0x180033759  lea     r9, [rsp+78h+dwBytes]
0x18003375e  mov     r8, rbx
0x180033761  mov     edx, 11000001h
0x180033766  mov     rcx, rbp
0x180033769  call    cs:__imp_BcdGetElementData
0x18003376f  mov     edi, eax
0x180033771  test    eax, eax
0x180033773  jns     short loc_180033789
0x180033775  lea     rdx, aBcdgetelementd_2; "BcdGetElementData failed: 0x%x"
0x18003377c  mov     r8d, eax
0x18003377f  mov     ecx, r12d
0x180033782  call    UnattendLogW
0x180033787  jmp     short loc_1800337EC
0x180033789  mov     rax, qword ptr cs:ZeroGuid.Data1
0x180033790  lea     rdx, [rbx+4]
0x180033794  sub     rax, [rdx]
0x180033797  jnz     short loc_1800337A4
0x180033799  mov     rax, qword ptr cs:ZeroGuid.Data4
0x1800337a0  sub     rax, [rdx+8]
0x1800337a4  test    rax, rax
0x1800337a7  jnz     short loc_1800337B0
0x1800337a9  mov     esi, 490h
0x1800337ae  jmp     short loc_1800337EC
0x1800337b0  lea     r8, [rsp+78h+var_48]
0x1800337b5  mov     rcx, r14
0x1800337b8  call    cs:__imp_BcdOpenObject
0x1800337be  mov     edi, eax
0x1800337c0  test    eax, eax
0x1800337c2  jns     short loc_1800337CD
0x1800337c4  lea     rdx, aBcdopenobjectF_0; "BcdOpenObject failed: 0x%x"
0x1800337cb  jmp     short loc_18003377C
0x1800337cd  mov     rcx, [rsp+78h+var_48]
0x1800337d2  call    cs:__imp_BcdDeleteObject
0x1800337d8  mov     edi, eax
0x1800337da  test    eax, eax
0x1800337dc  jns     short loc_1800337E7
0x1800337de  lea     rdx, aBcddeleteobjec_1; "BcdDeleteObject filed: 0x%x"
0x1800337e5  jmp     short loc_18003377C
0x1800337e7  mov     [rsp+78h+var_48], rsi
0x1800337ec  call    cs:__imp_GetProcessHeap
0x1800337f2  mov     r8, rbx; lpMem
0x1800337f5  xor     edx, edx; dwFlags
0x1800337f7  mov     rcx, rax; hHeap
0x1800337fa  call    cs:__imp_HeapFree
0x180033800  mov     rcx, [rsp+78h+var_48]
0x180033805  test    rcx, rcx
0x180033808  jz      short loc_180033819
0x18003380a  call    cs:__imp_BcdCloseObject
0x180033810  mov     [rsp+78h+var_48], 0
0x180033819  test    edi, edi
0x18003381b  jns     short loc_180033839
0x18003381d  mov     r8d, edi
0x180033820  lea     rdx, aWinredeleteram_0; "winreDeleteRamDiskObject failed: 0x%x"
0x180033827  mov     ecx, r12d
0x18003382a  call    UnattendLogW
0x18003382f  mov     ecx, edi; Status
0x180033831  call    cs:__imp_RtlNtStatusToDosError
0x180033837  mov     esi, eax
0x180033839  mov     eax, esi
0x18003383b  mov     rcx, [rsp+78h+var_38]
0x180033840  xor     rcx, rsp; StackCookie
0x180033843  call    __security_check_cookie
0x180033848  mov     rbx, [rsp+78h+arg_10]
0x180033850  add     rsp, 50h
0x180033854  pop     r14
0x180033856  pop     r12
0x180033858  pop     rdi
0x180033859  pop     rsi
0x18003385a  pop     rbp
0x18003385b  retn
```
