# CreateQueueEvent(FAX_ENUM_JOB_EVENT_TYPE,_JOB_QUEUE * const)

- ea: `0x14005900c`
- end: `0x1400592a5`
- name: `?CreateQueueEvent@@YAKW4FAX_ENUM_JOB_EVENT_TYPE@@QEAU_JOB_QUEUE@@@Z`
- size: `665`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `7`
- tags: ``

## callers

- `0x140016690`
- `0x14001dbc0`
- `0x140030cf0`
- `0x140031d80`
- `0x140032e04`
- `0x14003354c`
- `0x140034da0`
- `0x1400354cc`
- `0x140036268`
- `0x14003b300`
- `0x14003bf3c`
- `0x14003d470`
- `0x14003da4c`
- `0x14003fa40`
- `0x1400411a0`
- `0x140044164`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140014678`
- `0x14005900c`
- `0x14005adb4`
- `0x1400698ec`
- `0x14006998c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005909d`
- `KERNEL32!GetLastError` at `0x140059174`
- `KERNEL32!GetLastError` at `0x14005909d`
- `KERNEL32!GetLastError` at `0x140059174`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14005921a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14005921a`

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
  DWORD v21; // eax
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
  if ( (unsigned int)GetJobStatusDataEx(0, 0, 0x10000u, (struct _JOB_QUEUE *const)a2, &dwBytes, 0) )
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
    if ( !(unsigned int)GetJobStatusDataEx(
                          (unsigned __int8 *)v11,
                          v15,
                          0x10000u,
                          (struct _JOB_QUEUE *const)a2,
                          &dwBytes,
                          v10) )
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
0x14005900c  push    rbx
0x14005900e  push    rbp
0x14005900f  push    rsi
0x140059010  push    rdi
0x140059011  push    r14
0x140059013  push    r15
0x140059015  sub     rsp, 38h
0x140059019  mov     rdi, rdx
0x14005901c  mov     ebp, ecx
0x14005901e  mov     rcx, cs:WPP_GLOBAL_Control
0x140059025  lea     r14, WPP_GLOBAL_Control
0x14005902c  cmp     rcx, r14
0x14005902f  jz      short loc_140059052
0x140059031  test    byte ptr [rcx+1Ch], 4
0x140059035  jz      short loc_140059052
0x140059037  cmp     byte ptr [rcx+19h], 5
0x14005903b  jb      short loc_140059052
0x14005903d  mov     rcx, [rcx+10h]
0x140059041  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140059048  mov     edx, 64h ; 'd'
0x14005904d  call    WPP_SF_
0x140059052  mov     r15, [rdi+10h]
0x140059056  xor     esi, esi
0x140059058  cmp     dword ptr [rdi+24h], 2
0x14005905c  mov     eax, 38h ; '8'
0x140059061  mov     [rsp+68h+dwBytes], rax
0x140059066  setz    sil
0x14005906a  inc     esi
0x14005906c  cmp     ebp, 1
0x14005906f  jbe     loc_1400591BA
0x140059075  lea     rax, [rsp+68h+dwBytes]
0x14005907a  mov     [rsp+68h+var_40], 0; unsigned int
0x140059082  mov     r9, rdi; struct _JOB_QUEUE *
0x140059085  mov     [rsp+68h+var_48], rax; unsigned __int64 *
0x14005908a  xor     edx, edx; struct _FAX_JOB_STATUSW *
0x14005908c  xor     ecx, ecx; unsigned __int8 *
0x14005908e  mov     r8d, 10000h; unsigned int
0x140059094  call    ?GetJobStatusDataEx@@YAHPEAEPEAU_FAX_JOB_STATUSW@@KQEAU_JOB_QUEUE@@PEA_KK@Z; GetJobStatusDataEx(uchar *,_FAX_JOB_STATUSW *,ulong,_JOB_QUEUE * const,unsigned __int64 *,ulong)
0x140059099  test    eax, eax
0x14005909b  jnz     short loc_1400590E2
0x14005909d  call    cs:__imp_GetLastError
0x1400590a4  nop     dword ptr [rax+rax+00h]
0x1400590a9  mov     ebx, eax
0x1400590ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400590b2  cmp     rcx, r14
0x1400590b5  jz      short loc_1400590DB
0x1400590b7  test    byte ptr [rcx+1Ch], 4
0x1400590bb  jz      short loc_1400590DB
0x1400590bd  cmp     byte ptr [rcx+19h], 2
0x1400590c1  jb      short loc_1400590DB
0x1400590c3  mov     rcx, [rcx+10h]
0x1400590c7  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x1400590ce  mov     edx, 66h ; 'f'
0x1400590d3  mov     r9d, eax
0x1400590d6  call    WPP_SF_d
0x1400590db  mov     eax, ebx
0x1400590dd  jmp     loc_140059297
0x1400590e2  mov     r14d, dword ptr [rsp+68h+dwBytes]
0x1400590e7  mov     ecx, r14d; dwBytes
0x1400590ea  call    pMemAlloc
0x1400590ef  mov     rbx, rax
0x1400590f2  test    rax, rax
0x1400590f5  jnz     short loc_14005912A
0x1400590f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400590fe  lea     rax, WPP_GLOBAL_Control
0x140059105  cmp     rcx, rax
0x140059108  jz      loc_1400591F5
0x14005910e  test    byte ptr [rcx+1Ch], 4
0x140059112  jz      loc_1400591F5
0x140059118  cmp     byte ptr [rcx+19h], 2
0x14005911c  jb      loc_1400591F5
0x140059122  lea     edx, [rbx+67h]
0x140059125  jmp     loc_1400591E5
0x14005912a  mov     eax, 38h ; '8'
0x14005912f  mov     [rsp+68h+var_40], r14d; unsigned int
0x140059134  mov     [rsp+68h+dwBytes], rax
0x140059139  mov     r9, rdi; struct _JOB_QUEUE *
0x14005913c  mov     [rbx+20h], rax
0x140059140  mov     r8d, 10000h; unsigned int
0x140059146  mov     rax, [rsp+68h+dwBytes]
0x14005914b  mov     rcx, rbx; unsigned __int8 *
0x14005914e  lea     rdx, [rbx+rax]; struct _FAX_JOB_STATUSW *
0x140059152  add     rax, 0A0h
0x140059158  mov     [rsp+68h+dwBytes], rax
0x14005915d  lea     rax, [rsp+68h+dwBytes]
0x140059162  mov     [rsp+68h+var_48], rax; unsigned __int64 *
0x140059167  call    ?GetJobStatusDataEx@@YAHPEAEPEAU_FAX_JOB_STATUSW@@KQEAU_JOB_QUEUE@@PEA_KK@Z; GetJobStatusDataEx(uchar *,_FAX_JOB_STATUSW *,ulong,_JOB_QUEUE * const,unsigned __int64 *,ulong)
0x14005916c  test    eax, eax
0x14005916e  jnz     loc_140059209
0x140059174  call    cs:__imp_GetLastError
0x14005917b  nop     dword ptr [rax+rax+00h]
0x140059180  mov     edi, eax
0x140059182  mov     rcx, cs:WPP_GLOBAL_Control
0x140059189  lea     rax, WPP_GLOBAL_Control
0x140059190  cmp     rcx, rax
0x140059193  jz      loc_14005928D
0x140059199  test    byte ptr [rcx+1Ch], 4
0x14005919d  jz      loc_14005928D
0x1400591a3  cmp     byte ptr [rcx+19h], 2
0x1400591a7  jb      loc_14005928D
0x1400591ad  mov     edx, 68h ; 'h'
0x1400591b2  mov     r9d, edi
0x1400591b5  jmp     loc_14005927D
0x1400591ba  mov     rcx, rax; dwBytes
0x1400591bd  call    pMemAlloc
0x1400591c2  mov     rbx, rax
0x1400591c5  test    rax, rax
0x1400591c8  jnz     short loc_1400591FF
0x1400591ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400591d1  cmp     rcx, r14
0x1400591d4  jz      short loc_1400591F5
0x1400591d6  test    byte ptr [rcx+1Ch], 4
0x1400591da  jz      short loc_1400591F5
0x1400591dc  cmp     byte ptr [rcx+19h], 2
0x1400591e0  jb      short loc_1400591F5
0x1400591e2  lea     edx, [rax+65h]
0x1400591e5  mov     rcx, [rcx+10h]
0x1400591e9  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x1400591f0  call    WPP_SF_
0x1400591f5  mov     eax, 0Eh
0x1400591fa  jmp     loc_140059297
0x1400591ff  mov     qword ptr [rax+20h], 0
0x140059207  jmp     short loc_140059210
0x140059209  lea     r14, WPP_GLOBAL_Control
0x140059210  lea     rcx, [rbx+4]; lpSystemTimeAsFileTime
0x140059214  mov     dword ptr [rbx], 38h ; '8'
0x14005921a  call    cs:__imp_GetSystemTimeAsFileTime
0x140059221  nop     dword ptr [rax+rax+00h]
0x140059226  mov     [rbx+0Ch], esi
0x140059229  mov     [rbx+10h], r15
0x14005922d  mov     [rbx+18h], ebp
0x140059230  mov     dword ptr [rbx+28h], 0
0x140059237  cmp     dword ptr [rdi+24h], 2
0x14005923b  jnz     short loc_140059244
0x14005923d  mov     rdi, [rdi+248h]
0x140059244  mov     r8, [rdi+198h]; void *
0x14005924b  mov     rcx, rbx; struct _FAX_EVENT_EX_1 *
0x14005924e  mov     edx, dword ptr [rsp+68h+dwBytes]; unsigned int
0x140059252  call    ?PostFaxEventEx@@YAKPEAU_FAX_EVENT_EX_1@@KPEAX@Z; PostFaxEventEx(_FAX_EVENT_EX_1 *,ulong,void *)
0x140059257  mov     edi, eax
0x140059259  test    eax, eax
0x14005925b  jz      short loc_14005928D
0x14005925d  mov     rcx, cs:WPP_GLOBAL_Control
0x140059264  cmp     rcx, r14
0x140059267  jz      short loc_14005928D
0x140059269  test    byte ptr [rcx+1Ch], 4
0x14005926d  jz      short loc_14005928D
0x14005926f  cmp     byte ptr [rcx+19h], 2
0x140059273  jb      short loc_14005928D
0x140059275  mov     edx, 69h ; 'i'
0x14005927a  mov     r9d, eax
0x14005927d  mov     rcx, [rcx+10h]
0x140059281  lea     r8, WPP_37c06c2b2ac2386399119b86f8c474cd_Traceguids
0x140059288  call    WPP_SF_d
0x14005928d  mov     rcx, rbx; lpMem
0x140059290  call    pMemFree
0x140059295  mov     eax, edi
0x140059297  add     rsp, 38h
0x14005929b  pop     r15
0x14005929d  pop     r14
0x14005929f  pop     rdi
0x1400592a0  pop     rsi
0x1400592a1  pop     rbp
0x1400592a2  pop     rbx
0x1400592a3  retn
```
