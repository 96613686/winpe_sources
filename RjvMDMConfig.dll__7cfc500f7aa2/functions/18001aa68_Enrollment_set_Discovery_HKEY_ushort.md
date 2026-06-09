# Enrollment::set_Discovery(HKEY__ *,ushort *)

- ea: `0x18001aa68`
- end: `0x18001ab82`
- name: `?set_Discovery@Enrollment@@QEAAJPEAUHKEY__@@PEAG@Z`
- size: `282`
- prototype: `int(Enrollment *__hidden this, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017ed8`

## callees

- `0x18000c5dc`
- `0x18001aa68`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001aafa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001aafa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aae6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001aae6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001aab3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ab3f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001aab3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ab3f`

## string_xrefs

- `0x18001aa8d`: `DiscoveryServiceFullURL`
- `0x18001ab24`: `DiscoveryServiceFullURL`

## pseudocode

```c
__int64 __fastcall Enrollment::set_Discovery(Enrollment *this, HKEY a2, unsigned __int16 *a3)
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
  ValueW = RegGetValueW(a2, a3, L"DiscoveryServiceFullURL", 2u, 0, 0, (LPDWORD)&dwBytes);
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
      v13 = RegGetValueW(a2, a3, L"DiscoveryServiceFullURL", 2u, 0, pvData, (LPDWORD)&dwBytes);
      CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release((char *)this + 1816);
      *((_QWORD *)this + 227) = pvData;
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
0x18001aa68  mov     r11, rsp
0x18001aa6b  push    rbx
0x18001aa6c  push    rbp
0x18001aa6d  push    rsi
0x18001aa6e  push    rdi
0x18001aa6f  push    r14
0x18001aa71  push    r15
0x18001aa73  sub     rsp, 48h
0x18001aa77  mov     rsi, r8
0x18001aa7a  mov     dword ptr [r11+20h], 0
0x18001aa82  mov     r14, rdx
0x18001aa85  lea     rax, [r11+20h]
0x18001aa89  mov     [r11-48h], rax
0x18001aa8d  lea     r8, aDiscoveryservi; "DiscoveryServiceFullURL"
0x18001aa94  mov     r15, rcx
0x18001aa97  mov     qword ptr [r11-50h], 0
0x18001aa9f  mov     r9d, 2; dwFlags
0x18001aaa5  mov     qword ptr [r11-58h], 0
0x18001aaad  mov     rdx, rsi; lpSubKey
0x18001aab0  mov     rcx, r14; hkey
0x18001aab3  call    cs:__imp_RegGetValueW
0x18001aaba  nop     dword ptr [rax+rax+00h]
0x18001aabf  mov     edi, eax
0x18001aac1  cmp     eax, 2
0x18001aac4  jnz     short loc_18001AACD
0x18001aac6  xor     eax, eax
0x18001aac8  jmp     loc_18001AB74
0x18001aacd  test    eax, eax
0x18001aacf  jz      short loc_18001AADF
0x18001aad1  jle     loc_18001AB72
0x18001aad7  movzx   edi, ax
0x18001aada  jmp     loc_18001AB6C
0x18001aadf  mov     ebx, dword ptr [rsp+78h+dwBytes]
0x18001aae6  call    cs:__imp_GetProcessHeap
0x18001aaed  nop     dword ptr [rax+rax+00h]
0x18001aaf2  mov     r8d, ebx; dwBytes
0x18001aaf5  xor     edx, edx; dwFlags
0x18001aaf7  mov     rcx, rax; hHeap
0x18001aafa  call    cs:__imp_HeapAlloc
0x18001ab01  nop     dword ptr [rax+rax+00h]
0x18001ab06  mov     rbp, rax
0x18001ab09  test    rax, rax
0x18001ab0c  jnz     short loc_18001AB15
0x18001ab0e  mov     edi, 8007000Eh
0x18001ab13  jmp     short loc_18001AB72
0x18001ab15  xor     edi, edi
0x18001ab17  lea     rax, [rsp+78h+dwBytes]
0x18001ab1f  mov     [rsp+78h+pcbData], rax; pcbData
0x18001ab24  lea     r8, aDiscoveryservi; "DiscoveryServiceFullURL"
0x18001ab2b  mov     [rsp+78h+pvData], rbp; pvData
0x18001ab30  mov     rdx, rsi; lpSubKey
0x18001ab33  mov     rcx, r14; hkey
0x18001ab36  mov     [rsp+78h+pdwType], rdi; pdwType
0x18001ab3b  lea     r9d, [rdi+2]; dwFlags
0x18001ab3f  call    cs:__imp_RegGetValueW
0x18001ab46  nop     dword ptr [rax+rax+00h]
0x18001ab4b  lea     rbx, [r15+718h]
0x18001ab52  mov     esi, eax
0x18001ab54  mov     rcx, rbx
0x18001ab57  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18001ab5c  mov     [rbx], rbp
0x18001ab5f  test    esi, esi
0x18001ab61  jz      short loc_18001AB72
0x18001ab63  jg      short loc_18001AB69
0x18001ab65  mov     edi, esi
0x18001ab67  jmp     short loc_18001AB72
0x18001ab69  movzx   edi, si
0x18001ab6c  or      edi, 80070000h
0x18001ab72  mov     eax, edi
0x18001ab74  add     rsp, 48h
0x18001ab78  pop     r15
0x18001ab7a  pop     r14
0x18001ab7c  pop     rdi
0x18001ab7d  pop     rsi
0x18001ab7e  pop     rbp
0x18001ab7f  pop     rbx
0x18001ab80  retn
```
