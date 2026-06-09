# Enrollment::set_SID(HKEY__ *,ushort *)

- ea: `0x18001ad90`
- end: `0x18001aeaa`
- name: `?set_SID@Enrollment@@QEAAJPEAUHKEY__@@PEAG@Z`
- size: `282`
- prototype: `int(Enrollment *__hidden this, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017ed8`

## callees

- `0x18000c5dc`
- `0x18001ad90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ae22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ae22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ae0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ae0e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001addb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ae67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001addb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ae67`

## pseudocode

```c
__int64 __fastcall Enrollment::set_SID(void **this, HKEY a2, unsigned __int16 *a3)
{
  LSTATUS ValueW; // eax
  unsigned int v7; // edi
  int v9; // edi
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  void *pvData; // rbp
  LSTATUS v13; // esi
  SIZE_T dwBytes; // [rsp+98h] [rbp+20h] BYREF

  LODWORD(dwBytes) = 0;
  ValueW = RegGetValueW(a2, a3, L"SID", 2u, 0, 0, (LPDWORD)&dwBytes);
  v7 = ValueW;
  if ( ValueW == 2 )
    return 0;
  if ( ValueW )
  {
    if ( ValueW > 0 )
    {
      v9 = (unsigned __int16)ValueW;
      return v9 | 0x80070000;
    }
  }
  else
  {
    v10 = dwBytes;
    ProcessHeap = GetProcessHeap();
    pvData = HeapAlloc(ProcessHeap, 0, v10);
    if ( pvData )
    {
      v7 = 0;
      v13 = RegGetValueW(a2, a3, L"SID", 2u, 0, pvData, (LPDWORD)&dwBytes);
      CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(this + 225);
      this[225] = pvData;
      if ( v13 )
      {
        if ( v13 > 0 )
        {
          v9 = (unsigned __int16)v13;
          return v9 | 0x80070000;
        }
        return (unsigned int)v13;
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18001ad90  mov     r11, rsp
0x18001ad93  push    rbx
0x18001ad94  push    rbp
0x18001ad95  push    rsi
0x18001ad96  push    rdi
0x18001ad97  push    r14
0x18001ad99  push    r15
0x18001ad9b  sub     rsp, 48h
0x18001ad9f  mov     rsi, r8
0x18001ada2  mov     dword ptr [r11+20h], 0
0x18001adaa  mov     r14, rdx
0x18001adad  lea     rax, [r11+20h]
0x18001adb1  mov     [r11-48h], rax
0x18001adb5  lea     r8, aSid; "SID"
0x18001adbc  mov     r15, rcx
0x18001adbf  mov     qword ptr [r11-50h], 0
0x18001adc7  mov     r9d, 2; dwFlags
0x18001adcd  mov     qword ptr [r11-58h], 0
0x18001add5  mov     rdx, rsi; lpSubKey
0x18001add8  mov     rcx, r14; hkey
0x18001addb  call    cs:__imp_RegGetValueW
0x18001ade2  nop     dword ptr [rax+rax+00h]
0x18001ade7  mov     edi, eax
0x18001ade9  cmp     eax, 2
0x18001adec  jnz     short loc_18001ADF5
0x18001adee  xor     eax, eax
0x18001adf0  jmp     loc_18001AE9C
0x18001adf5  test    eax, eax
0x18001adf7  jz      short loc_18001AE07
0x18001adf9  jle     loc_18001AE9A
0x18001adff  movzx   edi, ax
0x18001ae02  jmp     loc_18001AE94
0x18001ae07  mov     ebx, dword ptr [rsp+78h+dwBytes]
0x18001ae0e  call    cs:__imp_GetProcessHeap
0x18001ae15  nop     dword ptr [rax+rax+00h]
0x18001ae1a  mov     r8d, ebx; dwBytes
0x18001ae1d  xor     edx, edx; dwFlags
0x18001ae1f  mov     rcx, rax; hHeap
0x18001ae22  call    cs:__imp_HeapAlloc
0x18001ae29  nop     dword ptr [rax+rax+00h]
0x18001ae2e  mov     rbp, rax
0x18001ae31  test    rax, rax
0x18001ae34  jnz     short loc_18001AE3D
0x18001ae36  mov     edi, 8007000Eh
0x18001ae3b  jmp     short loc_18001AE9A
0x18001ae3d  xor     edi, edi
0x18001ae3f  lea     rax, [rsp+78h+dwBytes]
0x18001ae47  mov     [rsp+78h+pcbData], rax; pcbData
0x18001ae4c  lea     r8, aSid; "SID"
0x18001ae53  mov     [rsp+78h+pvData], rbp; pvData
0x18001ae58  mov     rdx, rsi; lpSubKey
0x18001ae5b  mov     rcx, r14; hkey
0x18001ae5e  mov     [rsp+78h+pdwType], rdi; pdwType
0x18001ae63  lea     r9d, [rdi+2]; dwFlags
0x18001ae67  call    cs:__imp_RegGetValueW
0x18001ae6e  nop     dword ptr [rax+rax+00h]
0x18001ae73  lea     rbx, [r15+708h]
0x18001ae7a  mov     esi, eax
0x18001ae7c  mov     rcx, rbx
0x18001ae7f  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18001ae84  mov     [rbx], rbp
0x18001ae87  test    esi, esi
0x18001ae89  jz      short loc_18001AE9A
0x18001ae8b  jg      short loc_18001AE91
0x18001ae8d  mov     edi, esi
0x18001ae8f  jmp     short loc_18001AE9A
0x18001ae91  movzx   edi, si
0x18001ae94  or      edi, 80070000h
0x18001ae9a  mov     eax, edi
0x18001ae9c  add     rsp, 48h
0x18001aea0  pop     r15
0x18001aea2  pop     r14
0x18001aea4  pop     rdi
0x18001aea5  pop     rsi
0x18001aea6  pop     rbp
0x18001aea7  pop     rbx
0x18001aea8  retn
```
