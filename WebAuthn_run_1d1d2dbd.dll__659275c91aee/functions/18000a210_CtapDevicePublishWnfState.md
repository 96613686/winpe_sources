# _CtapDevicePublishWnfState

- ea: `0x18000a210`
- end: `0x18000a4dd`
- name: `_CtapDevicePublishWnfState`
- size: `717`
- prototype: ``
- caller_count: `30`
- callee_count: `2`
- tags: ``

## callers

- `0x180008c00`
- `0x180009350`
- `0x180009ba4`
- `0x18002b1b8`
- `0x18002e250`
- `0x18004d288`
- `0x18004d574`
- `0x1800dd350`
- `0x1800e3fcc`
- `0x1800e4bb0`
- `0x1800e4f30`
- `0x1800e53cc`
- `0x1800e6540`
- `0x1800e9a70`
- `0x1800eb4e0`
- `0x1800ede00`
- `0x1800ee5f4`
- `0x1800ef978`
- `0x1800f1430`
- `0x1800f5744`
- `0x1800f5e90`
- `0x1800f83a4`
- `0x1800f87e4`
- `0x1800f99f0`
- `0x1800faf78`
- `0x1800fb85c`
- `0x1800fbcf4`
- `0x180107340`
- `0x1801082ac`
- `0x18012a8e4`

## callees

- `0x18000a210`
- `0x180053780`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a461`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a2b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a461`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a248`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a345`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a248`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a345`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a328`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a328`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a44a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a48a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a44a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a48a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a4a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a4a9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a49c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a49c`

## pseudocode

```c
void __fastcall CtapDevicePublishWnfState(DWORD a1, DWORD a2, int a3, int a4)
{
  unsigned int v5; // edi
  int v8; // ebp
  DWORD v9; // r14d
  int v10; // eax
  __int64 Buf1; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v12; // [rsp+28h] [rbp-40h]

  LODWORD(Buf1) = a1;
  HIDWORD(Buf1) = a2;
  v5 = a3;
  v8 = a1;
  v9 = a2;
  if ( a3 > 0 )
    v5 = (unsigned __int16)a3 | 0x80070000;
  v12 = v5;
  AcquireSRWLockExclusive(&stru_1801AF240);
  if ( a2 == 2 || a2 == 100 )
  {
    v10 = a1;
    if ( !HIDWORD(qword_1801AF1F8) )
      v10 = a1 | 1;
    if ( v10 )
    {
      LODWORD(qword_1801AF1F8) = v10 | qword_1801AF1F8;
      switch ( (_DWORD)qword_1801AF1F8 )
      {
        case 3:
          v9 = 203;
          break;
        case 5:
          v9 = 205;
          break;
        case 6:
          v9 = 206;
          break;
        case 7:
          v9 = 207;
          break;
        default:
          goto LABEL_11;
      }
      v8 = 0;
      HIDWORD(Buf1) = v9;
      LODWORD(Buf1) = 0;
    }
  }
LABEL_11:
  if ( !memcmp_0(&Buf1, &dword_1801AF1E0, 0xCu) )
    goto LABEL_12;
  if ( a2 < 2 )
  {
    if ( pti )
    {
      dword_1801AF1EC = 0;
      SetThreadpoolTimer(pti, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(pti, 1);
      CloseThreadpoolTimer(pti);
      pti = 0;
    }
    qword_1801AF1F8 = 0;
    dword_1801AF1E0 = v8;
    dword_1801AF1E4 = v9;
    dword_1801AF1E8 = v5;
  }
  else if ( dword_1801AF1E4 )
  {
    if ( pti || (pti = CreateThreadpoolTimer(CtapDeviceWnfStateTimerCallback, 0, 0)) != 0 )
    {
      AcquireSRWLockExclusive(&stru_1801AF238);
      if ( (unsigned int)(dword_1801AF1E4 - 301) <= 0x15 && a2 == 10 )
        goto LABEL_59;
      if ( !dword_1801AF1E0 || (unsigned int)dword_1801AF1E4 <= 2 || a4 )
      {
        if ( a2 != 101 )
          goto LABEL_57;
      }
      else if ( a1 == 1 )
      {
        if ( a2 - 5 > 1 )
        {
          if ( dword_1801AF1E0 != 1 || a2 < 9 && a2 <= dword_1801AF1E4 )
            goto LABEL_59;
LABEL_57:
          dword_1801AF1E0 = v8;
          dword_1801AF1E4 = v9;
          dword_1801AF1E8 = v5;
          if ( !dword_1801AF1EC )
          {
            Buf1 = -1000000;
            SetThreadpoolTimer(pti, (PFILETIME)&Buf1, 0, 0);
            dword_1801AF1EC = 1;
          }
          goto LABEL_59;
        }
        if ( dword_1801AF1E4 != 6 )
          goto LABEL_57;
      }
      else
      {
        if ( a1 == 4 )
        {
          switch ( a2 )
          {
            case 'd':
              if ( dword_1801AF1E4 == 103 )
                goto LABEL_59;
              break;
            case 'e':
              if ( dword_1801AF1E4 == 103 )
                goto LABEL_57;
              break;
            case 'g':
              break;
            default:
              goto LABEL_57;
          }
          if ( dword_1801AF1E0 == 1 )
          {
            if ( a2 == 100 || dword_1801AF1E4 != 9 || dword_1801AF1E8 != -2146893043 )
              goto LABEL_59;
          }
          else if ( dword_1801AF1E0 != 4 || (unsigned int)(dword_1801AF1E4 - 100) > 1 && a2 != 103 )
          {
            goto LABEL_59;
          }
          goto LABEL_57;
        }
        if ( a2 != 2 )
          goto LABEL_57;
      }
LABEL_59:
      ReleaseSRWLockExclusive(&stru_1801AF238);
    }
  }
LABEL_12:
  ReleaseSRWLockExclusive(&stru_1801AF240);
}

```

## disassembly

```asm
0x18000a210  push    rbx
0x18000a212  push    rbp
0x18000a213  push    rsi
0x18000a214  push    rdi
0x18000a215  push    r14
0x18000a217  push    r15
0x18000a219  sub     rsp, 38h
0x18000a21d  mov     dword ptr [rsp+68h+Buf1], ecx
0x18000a221  mov     r15d, r9d
0x18000a224  mov     dword ptr [rsp+68h+Buf1+4], edx
0x18000a228  mov     edi, r8d
0x18000a22b  mov     ebx, edx
0x18000a22d  mov     esi, ecx
0x18000a22f  mov     ebp, ecx
0x18000a231  mov     r14d, edx
0x18000a234  test    r8d, r8d
0x18000a237  jg      loc_18000A2C6
0x18000a23d  lea     rcx, stru_1801AF240; SRWLock
0x18000a244  mov     [rsp+68h+var_40], edi
0x18000a248  call    cs:__imp_AcquireSRWLockExclusive
0x18000a24e  cmp     ebx, 2
0x18000a251  jnz     short loc_18000A2BF
0x18000a253  mov     ecx, esi
0x18000a255  mov     eax, esi
0x18000a257  or      ecx, 1
0x18000a25a  cmp     dword ptr cs:qword_1801AF1F8+4, 0
0x18000a261  cmovz   eax, ecx
0x18000a264  test    eax, eax
0x18000a266  jz      short loc_18000A28A
0x18000a268  mov     ecx, dword ptr cs:qword_1801AF1F8
0x18000a26e  or      ecx, eax
0x18000a270  mov     dword ptr cs:qword_1801AF1F8, ecx
0x18000a276  sub     ecx, 3
0x18000a279  jz      short loc_18000A2ED
0x18000a27b  sub     ecx, 2
0x18000a27e  jz      short loc_18000A2E5
0x18000a280  sub     ecx, 1
0x18000a283  jz      short loc_18000A2DD
0x18000a285  cmp     ecx, 1
0x18000a288  jz      short loc_18000A2D5
0x18000a28a  mov     r8d, 0Ch; Size
0x18000a290  lea     rdx, dword_1801AF1E0; Buf2
0x18000a297  lea     rcx, [rsp+68h+Buf1]; Buf1
0x18000a29c  call    memcmp_0
0x18000a2a1  test    eax, eax
0x18000a2a3  jnz     short loc_18000A300
0x18000a2a5  lea     rcx, stru_1801AF240
0x18000a2ac  add     rsp, 38h
0x18000a2b0  pop     r15
0x18000a2b2  pop     r14
0x18000a2b4  pop     rdi
0x18000a2b5  pop     rsi
0x18000a2b6  pop     rbp
0x18000a2b7  pop     rbx
0x18000a2b8  jmp     cs:__imp_ReleaseSRWLockExclusive
0x18000a2bf  cmp     ebx, 64h ; 'd'
0x18000a2c2  jnz     short loc_18000A28A
0x18000a2c4  jmp     short loc_18000A253
0x18000a2c6  movzx   edi, r8w
0x18000a2ca  or      edi, 80070000h
0x18000a2d0  jmp     loc_18000A23D
0x18000a2d5  mov     r14d, 0CFh
0x18000a2db  jmp     short loc_18000A2F3
0x18000a2dd  mov     r14d, 0CEh
0x18000a2e3  jmp     short loc_18000A2F3
0x18000a2e5  mov     r14d, 0CDh
0x18000a2eb  jmp     short loc_18000A2F3
0x18000a2ed  mov     r14d, 0CBh
0x18000a2f3  xor     ebp, ebp
0x18000a2f5  mov     dword ptr [rsp+68h+Buf1+4], r14d
0x18000a2fa  mov     dword ptr [rsp+68h+Buf1], ebp
0x18000a2fe  jmp     short loc_18000A28A
0x18000a300  cmp     ebx, 2
0x18000a303  jb      loc_18000A46C
0x18000a309  cmp     cs:dword_1801AF1E4, 0
0x18000a310  jz      short loc_18000A2A5
0x18000a312  cmp     cs:pti, 0
0x18000a31a  jnz     short loc_18000A33E
0x18000a31c  xor     r8d, r8d; pcbe
0x18000a31f  lea     rcx, CtapDeviceWnfStateTimerCallback; pfnti
0x18000a326  xor     edx, edx; pv
0x18000a328  call    cs:__imp_CreateThreadpoolTimer
0x18000a32e  mov     cs:pti, rax
0x18000a335  test    rax, rax
0x18000a338  jz      loc_18000A2A5
0x18000a33e  lea     rcx, stru_1801AF238; SRWLock
0x18000a345  call    cs:__imp_AcquireSRWLockExclusive
0x18000a34b  mov     ecx, cs:dword_1801AF1E4
0x18000a351  lea     eax, [rcx-12Dh]
0x18000a357  cmp     eax, 15h
0x18000a35a  ja      short loc_18000A365
0x18000a35c  cmp     ebx, 0Ah
0x18000a35f  jz      loc_18000A45A
0x18000a365  mov     edx, cs:dword_1801AF1E0
0x18000a36b  test    edx, edx
0x18000a36d  jz      loc_18000A40E
0x18000a373  cmp     ecx, 2
0x18000a376  jbe     loc_18000A40E
0x18000a37c  test    r15d, r15d
0x18000a37f  jnz     loc_18000A40E
0x18000a385  cmp     esi, 1
0x18000a388  jnz     short loc_18000A3B1
0x18000a38a  lea     eax, [rbx-5]
0x18000a38d  cmp     eax, esi
0x18000a38f  jbe     short loc_18000A3A7
0x18000a391  cmp     edx, esi
0x18000a393  jnz     loc_18000A45A
0x18000a399  cmp     ebx, 9
0x18000a39c  jnb     short loc_18000A413
0x18000a39e  cmp     ebx, ecx
0x18000a3a0  ja      short loc_18000A413
0x18000a3a2  jmp     loc_18000A45A
0x18000a3a7  cmp     ecx, 6
0x18000a3aa  jnz     short loc_18000A413
0x18000a3ac  jmp     loc_18000A45A
0x18000a3b1  cmp     esi, 4
0x18000a3b4  jnz     short loc_18000A407
0x18000a3b6  cmp     ebx, 64h ; 'd'
0x18000a3b9  jnz     short loc_18000A3C5
0x18000a3bb  cmp     ecx, 67h ; 'g'
0x18000a3be  jnz     short loc_18000A3D6
0x18000a3c0  jmp     loc_18000A45A
0x18000a3c5  cmp     ebx, 65h ; 'e'
0x18000a3c8  jnz     short loc_18000A3D1
0x18000a3ca  cmp     ecx, 67h ; 'g'
0x18000a3cd  jz      short loc_18000A413
0x18000a3cf  jmp     short loc_18000A3D6
0x18000a3d1  cmp     ebx, 67h ; 'g'
0x18000a3d4  jnz     short loc_18000A413
0x18000a3d6  cmp     edx, 1
0x18000a3d9  jnz     short loc_18000A3F3
0x18000a3db  cmp     ebx, 64h ; 'd'
0x18000a3de  jz      short loc_18000A45A
0x18000a3e0  cmp     ecx, 9
0x18000a3e3  jnz     short loc_18000A45A
0x18000a3e5  cmp     cs:dword_1801AF1E8, 8009030Dh
0x18000a3ef  jz      short loc_18000A413
0x18000a3f1  jmp     short loc_18000A45A
0x18000a3f3  cmp     edx, 4
0x18000a3f6  jnz     short loc_18000A45A
0x18000a3f8  lea     eax, [rcx-64h]
0x18000a3fb  cmp     eax, 1
0x18000a3fe  jbe     short loc_18000A413
0x18000a400  cmp     ebx, 67h ; 'g'
0x18000a403  jz      short loc_18000A413
0x18000a405  jmp     short loc_18000A45A
0x18000a407  cmp     ebx, 2
0x18000a40a  jnz     short loc_18000A413
0x18000a40c  jmp     short loc_18000A45A
0x18000a40e  cmp     ebx, 65h ; 'e'
0x18000a411  jz      short loc_18000A45A
0x18000a413  cmp     cs:dword_1801AF1EC, 0
0x18000a41a  mov     cs:dword_1801AF1E0, ebp
0x18000a420  mov     cs:dword_1801AF1E4, r14d
0x18000a427  mov     cs:dword_1801AF1E8, edi
0x18000a42d  jnz     short loc_18000A45A
0x18000a42f  mov     rcx, cs:pti; pti
0x18000a436  lea     rdx, [rsp+68h+Buf1]; pftDueTime
0x18000a43b  xor     r9d, r9d; msWindowLength
0x18000a43e  mov     [rsp+68h+Buf1], 0FFFFFFFFFFF0BDC0h
0x18000a447  xor     r8d, r8d; msPeriod
0x18000a44a  call    cs:__imp_SetThreadpoolTimer
0x18000a450  mov     cs:dword_1801AF1EC, 1
0x18000a45a  lea     rcx, stru_1801AF238; SRWLock
0x18000a461  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a467  jmp     loc_18000A2A5
0x18000a46c  mov     rcx, cs:pti; pti
0x18000a473  test    rcx, rcx
0x18000a476  jz      short loc_18000A4BA
0x18000a478  xor     r9d, r9d; msWindowLength
0x18000a47b  mov     cs:dword_1801AF1EC, 0
0x18000a485  xor     r8d, r8d; msPeriod
0x18000a488  xor     edx, edx; pftDueTime
0x18000a48a  call    cs:__imp_SetThreadpoolTimer
0x18000a490  mov     rcx, cs:pti; pti
0x18000a497  mov     edx, 1; fCancelPendingCallbacks
0x18000a49c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a4a2  mov     rcx, cs:pti; pti
0x18000a4a9  call    cs:__imp_CloseThreadpoolTimer
0x18000a4af  mov     cs:pti, 0
0x18000a4ba  mov     cs:qword_1801AF1F8, 0
0x18000a4c5  mov     cs:dword_1801AF1E0, ebp
0x18000a4cb  mov     cs:dword_1801AF1E4, r14d
0x18000a4d2  mov     cs:dword_1801AF1E8, edi
0x18000a4d8  jmp     loc_18000A2A5
```
