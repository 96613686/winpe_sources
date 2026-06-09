# BfspRemoveInvalidBcdEntry

- ea: `0x140008400`
- end: `0x14000868e`
- name: `BfspRemoveInvalidBcdEntry`
- size: `654`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x140003d30`

## callees

- `0x14000619c`
- `0x140006a14`
- `0x140008400`
- `0x140009170`
- `0x14000e628`
- `0x140013b48`
- `0x140013b9c`
- `0x140013ee8`
- `0x140026650`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000860a`
- `KERNEL32!HeapFree` at `0x140008623`
- `KERNEL32!HeapFree` at `0x14000863c`
- `KERNEL32!HeapFree` at `0x14000860a`
- `KERNEL32!HeapFree` at `0x140008623`
- `KERNEL32!HeapFree` at `0x14000863c`
- `KERNEL32!GetProcessHeap` at `0x1400085fb`
- `KERNEL32!GetProcessHeap` at `0x140008615`
- `KERNEL32!GetProcessHeap` at `0x14000862e`
- `KERNEL32!GetProcessHeap` at `0x1400085fb`
- `KERNEL32!GetProcessHeap` at `0x140008615`
- `KERNEL32!GetProcessHeap` at `0x14000862e`
- `ntdll!RtlStringFromGUID` at `0x14000850b`
- `ntdll!RtlStringFromGUID` at `0x14000850b`
- `ntdll!RtlFreeUnicodeString` at `0x14000864b`
- `ntdll!RtlFreeUnicodeString` at `0x14000864b`

## string_xrefs

- `0x1400085ae`: `Failed to delete duplicate loader object. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspRemoveInvalidBcdEntry(__int64 a1, _QWORD *a2)
{
  wchar_t *v2; // rbx
  void *v3; // r14
  int BcdElementData; // edi
  GUID v7; // xmm0
  HANDLE v8; // rsi
  int v9; // r12d
  int v10; // eax
  __int64 v11; // rdx
  HANDLE ProcessHeap; // rax
  HANDLE v13; // rax
  HANDLE v14; // rax
  int v16; // [rsp+30h] [rbp-39h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-31h] BYREF
  int v18; // [rsp+40h] [rbp-29h] BYREF
  int v19; // [rsp+44h] [rbp-25h] BYREF
  int v20; // [rsp+48h] [rbp-21h] BYREF
  wchar_t *v21; // [rsp+50h] [rbp-19h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-11h] BYREF
  void *v23; // [rsp+60h] [rbp-9h] BYREF
  HANDLE v24; // [rsp+68h] [rbp-1h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+70h] [rbp+7h] BYREF
  GUID Guid; // [rsp+80h] [rbp+17h] BYREF

  Handle = 0;
  v20 = 0;
  v2 = 0;
  v18 = 0;
  v3 = 0;
  v21 = 0;
  v23 = 0;
  Guid = 0;
  GuidString = 0;
  v19 = 0;
  v24 = 0;
  v16 = 1;
  lpMem = 0;
  BcdElementData = BcdOpenObject(a1, a2, &v24);
  if ( BcdElementData < 0 )
  {
    v8 = v24;
  }
  else
  {
    v7 = *(GUID *)a2;
    v8 = v24;
    v9 = 0;
    Guid = v7;
    BcdElementData = BfspGetBcdElementData((__int64)v24, 0x11000001u, &lpMem, &v18);
    if ( BcdElementData >= 0 )
    {
      BcdElementData = BfspGetBcdElementData((__int64)v8, 0x12000002u, &v23, &v19);
      if ( BcdElementData < 0 )
      {
        v3 = v23;
      }
      else
      {
        if ( (int)BfspGetBcdElementData((__int64)v8, 0x12000004u, &v21, &v20) >= 0 )
        {
          if ( RtlStringFromGUID(&Guid, &GuidString) >= 0 )
            v9 = 1;
          else
            GuidString.Buffer = L"Unknown";
          v2 = v21;
        }
        else
        {
          v2 = L"Unknown";
        }
        BfspLogMessage(2, L"Validating Device for %ws with identifier %ws", v2, GuidString.Buffer);
        v3 = v23;
        BcdElementData = BfspValidateDevice(a1, (_DWORD)v8, (_DWORD)lpMem, (_DWORD)v23, (__int64)&v16);
        BfspLogMessage(2, L"Done validating Device for %ws", v2);
        if ( BcdElementData >= 0 && !v16 )
        {
          BfspLogMessage(2, L"Deleting object %ws with GUID %ws", v2, GuidString.Buffer);
          v10 = BcdDeleteObject((__int64)v8);
          v8 = 0;
          BcdElementData = v10;
          if ( v10 >= 0 )
          {
            BcdElementData = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &Handle);
            if ( BcdElementData >= 0 )
            {
              BfspDeleteObjectFromDisplayOrder((__int64)Handle, v11, (__int64)&Guid);
              BcdCloseObject(Handle);
            }
          }
          else
          {
            BfspLogMessage(4, L"Failed to delete duplicate loader object. Status = [%x]", (unsigned int)v10);
          }
        }
      }
    }
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
    if ( v3 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v3);
    }
    if ( v2 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v2);
    }
    if ( v9 )
      RtlFreeUnicodeString(&GuidString);
  }
  if ( v8 )
    BcdCloseObject(v8);
  return (unsigned int)BcdElementData;
}

```

## disassembly

```asm
0x140008400  mov     [rsp-8+arg_10], rbx
0x140008405  mov     [rsp-8+arg_18], rsi
0x14000840a  push    rbp
0x14000840b  push    rdi
0x14000840c  push    r12
0x14000840e  push    r13
0x140008410  push    r14
0x140008412  lea     rbp, [rsp-37h]
0x140008417  sub     rsp, 0A0h
0x14000841e  mov     rax, cs:__security_cookie
0x140008425  xor     rax, rsp
0x140008428  mov     [rbp+57h+var_30], rax
0x14000842c  xorps   xmm0, xmm0
0x14000842f  mov     [rbp+57h+Handle], 0
0x140008437  xorps   xmm1, xmm1
0x14000843a  mov     [rbp+57h+var_78], 0
0x140008441  xor     ebx, ebx
0x140008443  mov     [rbp+57h+var_80], 0
0x14000844a  xor     r14d, r14d
0x14000844d  mov     [rbp+57h+var_70], rbx
0x140008451  lea     r8, [rbp+57h+var_58]
0x140008455  mov     [rbp+57h+var_60], r14
0x140008459  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x14000845d  mov     rsi, rdx
0x140008460  mov     r13, rcx
0x140008463  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm1
0x140008467  mov     [rbp+57h+var_7C], 0
0x14000846e  mov     [rbp+57h+var_58], 0
0x140008476  mov     [rbp+57h+var_90], 1
0x14000847d  mov     [rbp+57h+lpMem], 0
0x140008485  call    BcdOpenObject
0x14000848a  mov     edi, eax
0x14000848c  test    eax, eax
0x14000848e  js      loc_140008653
0x140008494  movups  xmm0, xmmword ptr [rsi]
0x140008497  mov     rsi, [rbp+57h+var_58]
0x14000849b  lea     r9, [rbp+57h+var_80]
0x14000849f  mov     rcx, rsi
0x1400084a2  lea     r8, [rbp+57h+lpMem]
0x1400084a6  mov     edx, 11000001h
0x1400084ab  xor     r12d, r12d
0x1400084ae  movdqu  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x1400084b3  call    BfspGetBcdElementData
0x1400084b8  mov     edi, eax
0x1400084ba  test    eax, eax
0x1400084bc  js      loc_1400085F4
0x1400084c2  lea     r9, [rbp+57h+var_7C]
0x1400084c6  mov     edx, 12000002h
0x1400084cb  lea     r8, [rbp+57h+var_60]
0x1400084cf  mov     rcx, rsi
0x1400084d2  call    BfspGetBcdElementData
0x1400084d7  mov     edi, eax
0x1400084d9  test    eax, eax
0x1400084db  js      loc_1400085F0
0x1400084e1  lea     r9, [rbp+57h+var_78]
0x1400084e5  mov     edx, 12000004h
0x1400084ea  lea     r8, [rbp+57h+var_70]
0x1400084ee  mov     rcx, rsi
0x1400084f1  call    BfspGetBcdElementData
0x1400084f6  test    eax, eax
0x1400084f8  jns     short loc_140008503
0x1400084fa  lea     rbx, aUnknown; "Unknown"
0x140008501  jmp     short loc_14000852C
0x140008503  lea     rdx, [rbp+57h+GuidString]; GuidString
0x140008507  lea     rcx, [rbp+57h+Guid]; Guid
0x14000850b  call    cs:__imp_RtlStringFromGUID
0x140008511  test    eax, eax
0x140008513  jns     short loc_140008522
0x140008515  lea     rbx, aUnknown; "Unknown"
0x14000851c  mov     [rbp+57h+GuidString.Buffer], rbx
0x140008520  jmp     short loc_140008528
0x140008522  mov     r12d, 1
0x140008528  mov     rbx, [rbp+57h+var_70]
0x14000852c  mov     r9, [rbp+57h+GuidString.Buffer]
0x140008530  lea     rdx, aValidatingDevi; "Validating Device for %ws with identifi"...
0x140008537  mov     r8, rbx
0x14000853a  mov     ecx, 2
0x14000853f  call    BfspLogMessage
0x140008544  mov     r14, [rbp+57h+var_60]
0x140008548  lea     rax, [rbp+57h+var_90]
0x14000854c  mov     r8, [rbp+57h+lpMem]
0x140008550  mov     r9, r14
0x140008553  mov     rdx, rsi
0x140008556  mov     [rsp+0C0h+var_A0], rax
0x14000855b  mov     rcx, r13
0x14000855e  call    BfspValidateDevice
0x140008563  mov     r8, rbx
0x140008566  lea     rdx, aDoneValidating_2; "Done validating Device for %ws"
0x14000856d  mov     ecx, 2
0x140008572  mov     edi, eax
0x140008574  call    BfspLogMessage
0x140008579  test    edi, edi
0x14000857b  js      short loc_1400085F4
0x14000857d  cmp     [rbp+57h+var_90], 0
0x140008581  jnz     short loc_1400085F4
0x140008583  mov     r9, [rbp+57h+GuidString.Buffer]
0x140008587  lea     rdx, aDeletingObject; "Deleting object %ws with GUID %ws"
0x14000858e  mov     r8, rbx
0x140008591  mov     ecx, 2
0x140008596  call    BfspLogMessage
0x14000859b  mov     rcx, rsi
0x14000859e  call    BcdDeleteObject
0x1400085a3  xor     esi, esi
0x1400085a5  mov     edi, eax
0x1400085a7  test    eax, eax
0x1400085a9  jns     short loc_1400085BF
0x1400085ab  mov     r8d, eax
0x1400085ae  lea     rdx, aFailedToDelete_5; "Failed to delete duplicate loader objec"...
0x1400085b5  lea     ecx, [rsi+4]
0x1400085b8  call    BfspLogMessage
0x1400085bd  jmp     short loc_1400085F4
0x1400085bf  lea     r8, [rbp+57h+Handle]
0x1400085c3  mov     rcx, r13
0x1400085c6  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1400085cd  call    BcdOpenObject
0x1400085d2  mov     edi, eax
0x1400085d4  test    eax, eax
0x1400085d6  js      short loc_1400085F4
0x1400085d8  mov     rcx, [rbp+57h+Handle]
0x1400085dc  lea     r8, [rbp+57h+Guid]
0x1400085e0  call    BfspDeleteObjectFromDisplayOrder
0x1400085e5  mov     rcx, [rbp+57h+Handle]; Handle
0x1400085e9  call    BcdCloseObject
0x1400085ee  jmp     short loc_1400085F4
0x1400085f0  mov     r14, [rbp+57h+var_60]
0x1400085f4  cmp     [rbp+57h+lpMem], 0
0x1400085f9  jz      short loc_140008610
0x1400085fb  call    cs:__imp_GetProcessHeap
0x140008601  mov     r8, [rbp+57h+lpMem]; lpMem
0x140008605  xor     edx, edx; dwFlags
0x140008607  mov     rcx, rax; hHeap
0x14000860a  call    cs:__imp_HeapFree
0x140008610  test    r14, r14
0x140008613  jz      short loc_140008629
0x140008615  call    cs:__imp_GetProcessHeap
0x14000861b  mov     r8, r14; lpMem
0x14000861e  xor     edx, edx; dwFlags
0x140008620  mov     rcx, rax; hHeap
0x140008623  call    cs:__imp_HeapFree
0x140008629  test    rbx, rbx
0x14000862c  jz      short loc_140008642
0x14000862e  call    cs:__imp_GetProcessHeap
0x140008634  mov     r8, rbx; lpMem
0x140008637  xor     edx, edx; dwFlags
0x140008639  mov     rcx, rax; hHeap
0x14000863c  call    cs:__imp_HeapFree
0x140008642  test    r12d, r12d
0x140008645  jz      short loc_140008657
0x140008647  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x14000864b  call    cs:__imp_RtlFreeUnicodeString
0x140008651  jmp     short loc_140008657
0x140008653  mov     rsi, [rbp+57h+var_58]
0x140008657  test    rsi, rsi
0x14000865a  jz      short loc_140008664
0x14000865c  mov     rcx, rsi; Handle
0x14000865f  call    BcdCloseObject
0x140008664  mov     eax, edi
0x140008666  mov     rcx, [rbp+57h+var_30]
0x14000866a  xor     rcx, rsp; StackCookie
0x14000866d  call    __security_check_cookie
0x140008672  lea     r11, [rsp+0C0h+var_20]
0x14000867a  mov     rbx, [r11+40h]
0x14000867e  mov     rsi, [r11+48h]
0x140008682  mov     rsp, r11
0x140008685  pop     r14
0x140008687  pop     r13
0x140008689  pop     r12
0x14000868b  pop     rdi
0x14000868c  pop     rbp
0x14000868d  retn
```
