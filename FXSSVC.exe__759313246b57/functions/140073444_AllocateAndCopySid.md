# AllocateAndCopySid

- ea: `0x140073444`
- end: `0x1400735e3`
- name: `AllocateAndCopySid`
- size: `415`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `10`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000d000`
- `0x14000d91c`
- `0x14000dd74`
- `0x1400311d0`
- `0x14003354c`
- `0x14003735c`
- `0x140057410`
- `0x14005757c`
- `0x140057924`
- `0x1400579f8`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400698ec`
- `0x14006998c`
- `0x140073444`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x140073521`
- `ADVAPI32!GetLengthSid` at `0x140073521`
- `ADVAPI32!IsValidSid` at `0x1400734c3`
- `ADVAPI32!IsValidSid` at `0x1400734c3`
- `ADVAPI32!CopySid` at `0x140073577`
- `ADVAPI32!CopySid` at `0x140073577`
- `KERNEL32!GetLastError` at `0x1400734d3`
- `KERNEL32!GetLastError` at `0x140073587`
- `KERNEL32!GetLastError` at `0x1400734d3`
- `KERNEL32!GetLastError` at `0x140073587`

## pseudocode

```c
__int64 __fastcall AllocateAndCopySid(PSID pSourceSid, LPVOID *a2)
{
  CMapDeviceId *v4; // rcx
  DWORD v5; // ebx
  DWORD LastError; // eax
  DWORD LengthSid; // esi
  void *v8; // rax
  DWORD v10; // eax

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !pSourceSid )
  {
    if ( v4 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
      WPP_SF_(*((_QWORD *)v4 + 2), 21, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids);
    v5 = 0;
LABEL_28:
    *a2 = 0;
    return v5;
  }
  if ( !IsValidSid(pSourceSid) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, LastError);
    }
    return v5;
  }
  LengthSid = GetLengthSid(pSourceSid);
  v8 = (void *)pMemAlloc(LengthSid);
  *a2 = v8;
  if ( v8 )
  {
    if ( !CopySid(LengthSid, v8, pSourceSid) )
    {
      v10 = GetLastError();
      v5 = v10;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, v10);
      }
      pMemFree(*a2);
      goto LABEL_28;
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, LengthSid);
    }
    return 14;
  }
}

```

## disassembly

```asm
0x140073444  push    rbx
0x140073446  push    rsi
0x140073447  push    rdi
0x140073448  push    r14
0x14007344a  push    r15
0x14007344c  sub     rsp, 20h
0x140073450  mov     rdi, rdx
0x140073453  mov     rbx, rcx
0x140073456  mov     rcx, cs:WPP_GLOBAL_Control
0x14007345d  lea     r14, WPP_GLOBAL_Control
0x140073464  lea     r15, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x14007346b  cmp     rcx, r14
0x14007346e  jz      short loc_140073494
0x140073470  test    byte ptr [rcx+1Ch], 2
0x140073474  jz      short loc_140073494
0x140073476  cmp     byte ptr [rcx+19h], 5
0x14007347a  jb      short loc_140073494
0x14007347c  mov     rcx, [rcx+10h]
0x140073480  mov     edx, 14h
0x140073485  mov     r8, r15
0x140073488  call    WPP_SF_
0x14007348d  mov     rcx, cs:WPP_GLOBAL_Control
0x140073494  test    rbx, rbx
0x140073497  jnz     short loc_1400734C0
0x140073499  cmp     rcx, r14
0x14007349c  jz      short loc_1400734B9
0x14007349e  test    byte ptr [rcx+1Ch], 2
0x1400734a2  jz      short loc_1400734B9
0x1400734a4  cmp     byte ptr [rcx+19h], 5
0x1400734a8  jb      short loc_1400734B9
0x1400734aa  mov     rcx, [rcx+10h]
0x1400734ae  lea     edx, [rbx+15h]
0x1400734b1  mov     r8, r15
0x1400734b4  call    WPP_SF_
0x1400734b9  xor     ebx, ebx
0x1400734bb  jmp     loc_1400735C9
0x1400734c0  mov     rcx, rbx; pSid
0x1400734c3  call    cs:__imp_IsValidSid
0x1400734ca  nop     dword ptr [rax+rax+00h]
0x1400734cf  test    eax, eax
0x1400734d1  jnz     short loc_14007351E
0x1400734d3  call    cs:__imp_GetLastError
0x1400734da  nop     dword ptr [rax+rax+00h]
0x1400734df  mov     ebx, eax
0x1400734e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400734e8  cmp     rcx, r14
0x1400734eb  jz      loc_1400735D0
0x1400734f1  test    byte ptr [rcx+1Ch], 2
0x1400734f5  jz      loc_1400735D0
0x1400734fb  cmp     byte ptr [rcx+19h], 2
0x1400734ff  jb      loc_1400735D0
0x140073505  mov     rcx, [rcx+10h]
0x140073509  mov     edx, 16h
0x14007350e  mov     r9d, eax
0x140073511  mov     r8, r15
0x140073514  call    WPP_SF_d
0x140073519  jmp     loc_1400735D0
0x14007351e  mov     rcx, rbx; pSid
0x140073521  call    cs:__imp_GetLengthSid
0x140073528  nop     dword ptr [rax+rax+00h]
0x14007352d  mov     ecx, eax; dwBytes
0x14007352f  mov     esi, eax
0x140073531  call    pMemAlloc
0x140073536  mov     [rdi], rax
0x140073539  test    rax, rax
0x14007353c  jnz     short loc_14007356F
0x14007353e  mov     rcx, cs:WPP_GLOBAL_Control
0x140073545  cmp     rcx, r14
0x140073548  jz      short loc_140073568
0x14007354a  test    byte ptr [rcx+1Ch], 2
0x14007354e  jz      short loc_140073568
0x140073550  cmp     byte ptr [rcx+19h], 2
0x140073554  jb      short loc_140073568
0x140073556  mov     rcx, [rcx+10h]
0x14007355a  lea     edx, [rax+17h]
0x14007355d  mov     r9d, esi
0x140073560  mov     r8, r15
0x140073563  call    WPP_SF_d
0x140073568  mov     eax, 0Eh
0x14007356d  jmp     short loc_1400735D6
0x14007356f  mov     r8, rbx; pSourceSid
0x140073572  mov     rdx, rax; pDestinationSid
0x140073575  mov     ecx, esi; nDestinationSidLength
0x140073577  call    cs:__imp_CopySid
0x14007357e  nop     dword ptr [rax+rax+00h]
0x140073583  test    eax, eax
0x140073585  jnz     short loc_1400735D4
0x140073587  call    cs:__imp_GetLastError
0x14007358e  nop     dword ptr [rax+rax+00h]
0x140073593  mov     ebx, eax
0x140073595  mov     rcx, cs:WPP_GLOBAL_Control
0x14007359c  cmp     rcx, r14
0x14007359f  jz      short loc_1400735C1
0x1400735a1  test    byte ptr [rcx+1Ch], 2
0x1400735a5  jz      short loc_1400735C1
0x1400735a7  cmp     byte ptr [rcx+19h], 2
0x1400735ab  jb      short loc_1400735C1
0x1400735ad  mov     rcx, [rcx+10h]
0x1400735b1  mov     edx, 18h
0x1400735b6  mov     r9d, eax
0x1400735b9  mov     r8, r15
0x1400735bc  call    WPP_SF_d
0x1400735c1  mov     rcx, [rdi]; lpMem
0x1400735c4  call    pMemFree
0x1400735c9  mov     qword ptr [rdi], 0
0x1400735d0  mov     eax, ebx
0x1400735d2  jmp     short loc_1400735D6
0x1400735d4  xor     eax, eax
0x1400735d6  add     rsp, 20h
0x1400735da  pop     r15
0x1400735dc  pop     r14
0x1400735de  pop     rdi
0x1400735df  pop     rsi
0x1400735e0  pop     rbx
0x1400735e1  retn
```
