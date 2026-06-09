# CreateQueueEvent(FAX_ENUM_JOB_EVENT_TYPE,_JOB_QUEUE * const)

- ea: `0x140055acc`
- end: `0x140055d52`
- name: `?CreateQueueEvent@@YAKW4FAX_ENUM_JOB_EVENT_TYPE@@QEAU_JOB_QUEUE@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `16`
- callee_count: `7`
- tags: ``

## callers

- `0x140015d90`
- `0x14001cf70`
- `0x14002f580`
- `0x140030520`
- `0x1400314a8`
- `0x140031b6c`
- `0x14003325c`
- `0x14003392c`
- `0x14003465c`
- `0x140039350`
- `0x140039eb0`
- `0x14003b2fc`
- `0x14003b880`
- `0x14003d704`
- `0x14003ed20`
- `0x140041a98`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140013e6c`
- `0x140055acc`
- `0x14005783c`
- `0x140065d14`
- `0x140065dbc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140055b5d`
- `KERNEL32!GetLastError` at `0x140055c2e`
- `KERNEL32!GetLastError` at `0x140055b5d`
- `KERNEL32!GetLastError` at `0x140055c2e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140055cce`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140055cce`

## pseudocode

```c
__int64 __fastcall CreateQueueEvent(unsigned int a1, __int64 a2)
{
  __int64 v4; // r15
  bool v5; // zf
  int v6; // esi
  DWORD v7; // eax
  DWORD v8; // ebx
  unsigned int v10; // r14d
  __int64 v11; // rax
  _DWORD *v12; // rbx
  CMapDeviceId *v13; // rcx
  __int64 v14; // rdx
  struct _FAX_JOB_STATUSW *v15; // rdx
  DWORD LastError; // edi
  CMapDeviceId *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 v20; // rax
  unsigned int v21; // eax
  SIZE_T dwBytes; // [rsp+78h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
  }
  v4 = *(_QWORD *)(a2 + 16);
  v5 = *(_DWORD *)(a2 + 36) == 2;
  dwBytes = 56;
  v6 = v5 + 1;
  if ( a1 <= 1 )
  {
    v20 = pMemAlloc(0x38u);
    v12 = (_DWORD *)v20;
    if ( !v20 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 14;
      }
      v14 = 101;
      goto LABEL_27;
    }
    *(_QWORD *)(v20 + 32) = 0;
    goto LABEL_30;
  }
  if ( GetJobStatusDataEx(0, 0, 0x10000u, (struct _JOB_QUEUE *const)a2, &dwBytes, 0) )
  {
    v10 = dwBytes;
    v11 = pMemAlloc((unsigned int)dwBytes);
    v12 = (_DWORD *)v11;
    if ( !v11 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 14;
      }
      v14 = 103;
LABEL_27:
      WPP_SF_(*((_QWORD *)v13 + 2), v14, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids);
      return 14;
    }
    dwBytes = 56;
    *(_QWORD *)(v11 + 32) = 56;
    v15 = (struct _FAX_JOB_STATUSW *)(v11 + dwBytes);
    dwBytes += 160LL;
    if ( !GetJobStatusDataEx((unsigned __int8 *)v11, v15, 0x10000u, (struct _JOB_QUEUE *const)a2, &dwBytes, v10) )
    {
      LastError = GetLastError();
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_38;
      }
      v18 = 104;
      v19 = LastError;
LABEL_37:
      WPP_SF_d(*((_QWORD *)v17 + 2), v18, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v19);
LABEL_38:
      pMemFree(v12);
      return LastError;
    }
LABEL_30:
    *v12 = 56;
    GetSystemTimeAsFileTime((LPFILETIME)(v12 + 1));
    v12[3] = v6;
    *((_QWORD *)v12 + 2) = v4;
    v12[6] = a1;
    v12[10] = 0;
    if ( *(_DWORD *)(a2 + 36) == 2 )
      a2 = *(_QWORD *)(a2 + 584);
    v21 = PostFaxEventEx((struct _FAX_EVENT_EX_1 *)v12, dwBytes, *(void **)(a2 + 408));
    LastError = v21;
    if ( !v21 )
      goto LABEL_38;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_38;
    }
    v18 = 105;
    v19 = v21;
    goto LABEL_37;
  }
  v7 = GetLastError();
  v8 = v7;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids, v7);
  }
  return v8;
}

```

## disassembly

```asm
0x140055acc  push    rbx
0x140055ace  push    rbp
0x140055acf  push    rsi
0x140055ad0  push    rdi
0x140055ad1  push    r14
0x140055ad3  push    r15
0x140055ad5  sub     rsp, 38h
0x140055ad9  mov     rdi, rdx
0x140055adc  mov     ebp, ecx
0x140055ade  mov     rcx, cs:WPP_GLOBAL_Control
0x140055ae5  lea     r14, WPP_GLOBAL_Control
0x140055aec  cmp     rcx, r14
0x140055aef  jz      short loc_140055B12
0x140055af1  test    byte ptr [rcx+1Ch], 4
0x140055af5  jz      short loc_140055B12
0x140055af7  cmp     byte ptr [rcx+19h], 5
0x140055afb  jb      short loc_140055B12
0x140055afd  mov     rcx, [rcx+10h]
0x140055b01  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140055b08  mov     edx, 64h ; 'd'
0x140055b0d  call    WPP_SF_
0x140055b12  mov     r15, [rdi+10h]
0x140055b16  xor     esi, esi
0x140055b18  cmp     dword ptr [rdi+24h], 2
0x140055b1c  mov     eax, 38h ; '8'
0x140055b21  mov     [rsp+68h+dwBytes], rax
0x140055b26  setz    sil
0x140055b2a  inc     esi
0x140055b2c  cmp     ebp, 1
0x140055b2f  jbe     loc_140055C6E
0x140055b35  lea     rax, [rsp+68h+dwBytes]
0x140055b3a  mov     [rsp+68h+var_40], 0; unsigned int
0x140055b42  mov     r9, rdi; struct _JOB_QUEUE *
0x140055b45  mov     [rsp+68h+var_48], rax; unsigned __int64 *
0x140055b4a  xor     edx, edx; struct _FAX_JOB_STATUSW *
0x140055b4c  xor     ecx, ecx; unsigned __int8 *
0x140055b4e  mov     r8d, 10000h; unsigned int
0x140055b54  call    ?GetJobStatusDataEx@@YAHPEAEPEAU_FAX_JOB_STATUSW@@KQEAU_JOB_QUEUE@@PEA_KK@Z; GetJobStatusDataEx(uchar *,_FAX_JOB_STATUSW *,ulong,_JOB_QUEUE * const,unsigned __int64 *,ulong)
0x140055b59  test    eax, eax
0x140055b5b  jnz     short loc_140055B9C
0x140055b5d  call    cs:__imp_GetLastError
0x140055b63  mov     ebx, eax
0x140055b65  mov     rcx, cs:WPP_GLOBAL_Control
0x140055b6c  cmp     rcx, r14
0x140055b6f  jz      short loc_140055B95
0x140055b71  test    byte ptr [rcx+1Ch], 4
0x140055b75  jz      short loc_140055B95
0x140055b77  cmp     byte ptr [rcx+19h], 2
0x140055b7b  jb      short loc_140055B95
0x140055b7d  mov     rcx, [rcx+10h]
0x140055b81  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140055b88  mov     edx, 66h ; 'f'
0x140055b8d  mov     r9d, eax
0x140055b90  call    WPP_SF_d
0x140055b95  mov     eax, ebx
0x140055b97  jmp     loc_140055D45
0x140055b9c  mov     r14d, dword ptr [rsp+68h+dwBytes]
0x140055ba1  mov     ecx, r14d; dwBytes
0x140055ba4  call    pMemAlloc
0x140055ba9  mov     rbx, rax
0x140055bac  test    rax, rax
0x140055baf  jnz     short loc_140055BE4
0x140055bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140055bb8  lea     rax, WPP_GLOBAL_Control
0x140055bbf  cmp     rcx, rax
0x140055bc2  jz      loc_140055CA9
0x140055bc8  test    byte ptr [rcx+1Ch], 4
0x140055bcc  jz      loc_140055CA9
0x140055bd2  cmp     byte ptr [rcx+19h], 2
0x140055bd6  jb      loc_140055CA9
0x140055bdc  lea     edx, [rbx+67h]
0x140055bdf  jmp     loc_140055C99
0x140055be4  mov     eax, 38h ; '8'
0x140055be9  mov     [rsp+68h+var_40], r14d; unsigned int
0x140055bee  mov     [rsp+68h+dwBytes], rax
0x140055bf3  mov     r9, rdi; struct _JOB_QUEUE *
0x140055bf6  mov     [rbx+20h], rax
0x140055bfa  mov     r8d, 10000h; unsigned int
0x140055c00  mov     rax, [rsp+68h+dwBytes]
0x140055c05  mov     rcx, rbx; unsigned __int8 *
0x140055c08  lea     rdx, [rbx+rax]; struct _FAX_JOB_STATUSW *
0x140055c0c  add     rax, 0A0h
0x140055c12  mov     [rsp+68h+dwBytes], rax
0x140055c17  lea     rax, [rsp+68h+dwBytes]
0x140055c1c  mov     [rsp+68h+var_48], rax; unsigned __int64 *
0x140055c21  call    ?GetJobStatusDataEx@@YAHPEAEPEAU_FAX_JOB_STATUSW@@KQEAU_JOB_QUEUE@@PEA_KK@Z; GetJobStatusDataEx(uchar *,_FAX_JOB_STATUSW *,ulong,_JOB_QUEUE * const,unsigned __int64 *,ulong)
0x140055c26  test    eax, eax
0x140055c28  jnz     loc_140055CBD
0x140055c2e  call    cs:__imp_GetLastError
0x140055c34  mov     edi, eax
0x140055c36  mov     rcx, cs:WPP_GLOBAL_Control
0x140055c3d  lea     rax, WPP_GLOBAL_Control
0x140055c44  cmp     rcx, rax
0x140055c47  jz      loc_140055D3B
0x140055c4d  test    byte ptr [rcx+1Ch], 4
0x140055c51  jz      loc_140055D3B
0x140055c57  cmp     byte ptr [rcx+19h], 2
0x140055c5b  jb      loc_140055D3B
0x140055c61  mov     edx, 68h ; 'h'
0x140055c66  mov     r9d, edi
0x140055c69  jmp     loc_140055D2B
0x140055c6e  mov     rcx, rax; dwBytes
0x140055c71  call    pMemAlloc
0x140055c76  mov     rbx, rax
0x140055c79  test    rax, rax
0x140055c7c  jnz     short loc_140055CB3
0x140055c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140055c85  cmp     rcx, r14
0x140055c88  jz      short loc_140055CA9
0x140055c8a  test    byte ptr [rcx+1Ch], 4
0x140055c8e  jz      short loc_140055CA9
0x140055c90  cmp     byte ptr [rcx+19h], 2
0x140055c94  jb      short loc_140055CA9
0x140055c96  lea     edx, [rax+65h]
0x140055c99  mov     rcx, [rcx+10h]
0x140055c9d  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140055ca4  call    WPP_SF_
0x140055ca9  mov     eax, 0Eh
0x140055cae  jmp     loc_140055D45
0x140055cb3  mov     qword ptr [rax+20h], 0
0x140055cbb  jmp     short loc_140055CC4
0x140055cbd  lea     r14, WPP_GLOBAL_Control
0x140055cc4  lea     rcx, [rbx+4]; lpSystemTimeAsFileTime
0x140055cc8  mov     dword ptr [rbx], 38h ; '8'
0x140055cce  call    cs:__imp_GetSystemTimeAsFileTime
0x140055cd4  mov     [rbx+0Ch], esi
0x140055cd7  mov     [rbx+10h], r15
0x140055cdb  mov     [rbx+18h], ebp
0x140055cde  mov     dword ptr [rbx+28h], 0
0x140055ce5  cmp     dword ptr [rdi+24h], 2
0x140055ce9  jnz     short loc_140055CF2
0x140055ceb  mov     rdi, [rdi+248h]
0x140055cf2  mov     r8, [rdi+198h]; void *
0x140055cf9  mov     rcx, rbx; struct _FAX_EVENT_EX_1 *
0x140055cfc  mov     edx, dword ptr [rsp+68h+dwBytes]; unsigned int
0x140055d00  call    ?PostFaxEventEx@@YAKPEAU_FAX_EVENT_EX_1@@KPEAX@Z; PostFaxEventEx(_FAX_EVENT_EX_1 *,ulong,void *)
0x140055d05  mov     edi, eax
0x140055d07  test    eax, eax
0x140055d09  jz      short loc_140055D3B
0x140055d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140055d12  cmp     rcx, r14
0x140055d15  jz      short loc_140055D3B
0x140055d17  test    byte ptr [rcx+1Ch], 4
0x140055d1b  jz      short loc_140055D3B
0x140055d1d  cmp     byte ptr [rcx+19h], 2
0x140055d21  jb      short loc_140055D3B
0x140055d23  mov     edx, 69h ; 'i'
0x140055d28  mov     r9d, eax
0x140055d2b  mov     rcx, [rcx+10h]
0x140055d2f  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140055d36  call    WPP_SF_d
0x140055d3b  mov     rcx, rbx; lpMem
0x140055d3e  call    pMemFree
0x140055d43  mov     eax, edi
0x140055d45  add     rsp, 38h
0x140055d49  pop     r15
0x140055d4b  pop     r14
0x140055d4d  pop     rdi
0x140055d4e  pop     rsi
0x140055d4f  pop     rbp
0x140055d50  pop     rbx
0x140055d51  retn
```
