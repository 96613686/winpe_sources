# MpHandleClose

- ea: `0x180078e00`
- end: `0x1800793f7`
- name: `MpHandleClose`
- size: `1527`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `112`
- callee_count: `24`
- tags: ``

## callers

- `0x180075280`
- `0x180075ed0`
- `0x180076160`
- `0x180076740`
- `0x180076b70`
- `0x180076df0`
- `0x180077070`
- `0x1800772d0`
- `0x18007c940`
- `0x18007dc78`
- `0x180081e20`
- `0x180085440`
- `0x180086c38`
- `0x180088690`
- `0x180088a20`
- `0x180088eb0`
- `0x18008f8b0`
- `0x18009321c`
- `0x18009c3c0`
- `0x18009c550`
- `0x18009db20`
- `0x18009dc80`
- `0x18009de00`
- `0x18009dfc0`
- `0x18009e330`
- `0x18009e520`
- `0x18009e6a0`
- `0x18009e820`
- `0x18009ea50`
- `0x18009ec40`
- `0x18009ee40`
- `0x18009f020`
- `0x18009f210`
- `0x18009f460`
- `0x18009fb90`
- `0x18009fdc0`
- `0x1800a03c0`
- `0x1800a0d70`
- `0x1800a0ee0`
- `0x1800a11e0`
- `0x1800a1380`
- `0x1800a1540`
- `0x1800a16d0`
- `0x1800a1870`
- `0x1800a1a60`
- `0x1800a1bd0`
- `0x1800a1d40`
- `0x1800a1ec0`
- `0x1800a2040`
- `0x1800a21c0`

## callees

- `0x18001f89c`
- `0x1800207d0`
- `0x180073384`
- `0x1800733a8`
- `0x180078030`
- `0x180078e00`
- `0x18007aee8`
- `0x18007b858`
- `0x18007c0f0`
- `0x18007c444`
- `0x18007e7bc`
- `0x18007ecd8`
- `0x18007ee64`
- `0x1800804d8`
- `0x180081b54`
- `0x180082974`
- `0x1800843a8`
- `0x180084ff8`
- `0x180089a40`
- `0x18008f610`
- `0x1800ad764`
- `0x1800b6978`
- `0x1800ba688`
- `0x180125920`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180078ff4`
- `KERNEL32!GetCurrentThreadId` at `0x180078ff4`

## pseudocode

```c
__int64 __fastcall MpHandleClose(unsigned int *lpMem, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // ebx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  void *v14; // rcx
  _BYTE *v15; // rcx
  __int64 v16; // rdx
  __int64 *v17; // r8
  int v18; // eax
  __int64 v19; // rdx
  __int64 *v20; // r8
  void *v21; // rbx
  __int64 v22; // rbp
  int v23; // ebx
  __int64 v24; // rcx
  volatile signed __int32 *v25; // rbx
  int v26; // eax
  void *v27; // rcx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  void *v34; // rcx
  void *v35; // rcx
  int v36; // eax
  void *v37; // rcx
  void *v38; // rbx

  v4 = 0;
  if ( lpMem )
  {
    v7 = *lpMem;
    if ( v7 > 8 )
    {
      v28 = v7 - 9;
      if ( !v28 )
      {
        v38 = (void *)*((_QWORD *)lpMem + 1);
        v15 = off_18019DE80;
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
        {
          sub_180073384(*((_QWORD *)off_18019DE80 + 2), 85, qword_180145AA8, a4);
          v15 = off_18019DE80;
        }
        if ( !v38 )
        {
          if ( v15 == (_BYTE *)&off_18019DE80 || (v15[28] & 1) == 0 )
            goto LABEL_21;
          v16 = 86;
LABEL_33:
          v17 = qword_180145AA8;
          goto LABEL_20;
        }
        v18 = sub_18007EE64(v38);
        v4 = v18;
        if ( v18 < 0 )
        {
          v15 = off_18019DE80;
          if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
            goto LABEL_119;
          v19 = 87;
LABEL_116:
          v20 = qword_180145AA8;
          goto LABEL_117;
        }
LABEL_118:
        v15 = off_18019DE80;
        goto LABEL_119;
      }
      v29 = v28 - 1;
      if ( !v29 )
      {
        v37 = (void *)*((_QWORD *)lpMem + 1);
        if ( !v37 )
        {
          v15 = off_18019DE80;
          if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
            goto LABEL_21;
          v16 = 27;
          v17 = qword_180145AB8;
          goto LABEL_20;
        }
        v18 = sub_1800804D8(v37);
        v4 = v18;
        if ( v18 >= 0 )
          goto LABEL_118;
        v15 = off_18019DE80;
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
        {
          v19 = 28;
          v20 = qword_180145AB8;
          goto LABEL_117;
        }
        goto LABEL_119;
      }
      v30 = v29 - 1;
      if ( !v30 )
      {
        v35 = (void *)*((_QWORD *)lpMem + 1);
        if ( !v35 )
        {
          v15 = off_18019DE80;
          if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
            goto LABEL_21;
          v16 = 29;
          v17 = qword_180146840;
          goto LABEL_20;
        }
        v36 = sub_18008F610(v35);
        v4 = v36;
        if ( v36 >= 0 )
          goto LABEL_118;
        v15 = off_18019DE80;
        if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
          goto LABEL_119;
        sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 30, qword_180146840, (unsigned int)v36);
        goto LABEL_118;
      }
      v31 = v30 - 1;
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( !v32 )
        {
          v34 = (void *)*((_QWORD *)lpMem + 1);
          if ( !v34 )
          {
            v15 = off_18019DE80;
            if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
              goto LABEL_21;
            v16 = 39;
            v17 = qword_180145AF8;
            goto LABEL_20;
          }
          v18 = sub_180084FF8(v34);
          v4 = v18;
          if ( v18 >= 0 )
            goto LABEL_118;
          v15 = off_18019DE80;
          if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          {
            v19 = 40;
            v20 = qword_180145AF8;
            goto LABEL_117;
          }
          goto LABEL_119;
        }
        v33 = v32 - 1;
        if ( v33 )
        {
          if ( v33 != 1 )
            goto LABEL_72;
          v25 = (volatile signed __int32 *)*((_QWORD *)lpMem + 1);
          if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 0x10) != 0 )
            sub_180073384(*((_QWORD *)off_18019DE80 + 2), 24, qword_180147848, a4);
          sub_1800BA688(v25);
        }
        else
        {
          v25 = (volatile signed __int32 *)*((_QWORD *)lpMem + 1);
          sub_1800B6978(v25);
        }
        if ( !v25 )
        {
LABEL_52:
          v4 = 0;
          goto LABEL_123;
        }
LABEL_50:
        if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v25)(v25, 1);
        }
        goto LABEL_52;
      }
      v26 = sub_1800AD764(*((_QWORD **)lpMem + 1));
    }
    else
    {
      if ( v7 == 8 )
      {
        v27 = (void *)*((_QWORD *)lpMem + 1);
        if ( !v27 )
        {
          v15 = off_18019DE80;
          if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
            goto LABEL_21;
          v16 = 37;
          v17 = qword_180145AD8;
          goto LABEL_20;
        }
        v18 = sub_180082974(v27);
        v4 = v18;
        if ( v18 >= 0 )
          goto LABEL_118;
        v15 = off_18019DE80;
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
        {
          v19 = 38;
          v20 = qword_180145AD8;
          goto LABEL_117;
        }
LABEL_119:
        if ( v4 < 0 )
          goto LABEL_120;
LABEL_123:
        MpFreeMemory(lpMem);
        return (unsigned int)v4;
      }
      if ( !v7 )
        goto LABEL_123;
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              v12 = v11 - 1;
              if ( !v12 )
              {
                v22 = *((_QWORD *)lpMem + 1);
                if ( !v22 )
                {
                  v15 = off_18019DE80;
                  if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
                    goto LABEL_21;
                  v16 = 17;
                  v17 = qword_1801459D0;
                  goto LABEL_20;
                }
                sub_18001F89C(*(_QWORD *)(v22 + 88));
                v23 = *(_DWORD *)(v22 + 96);
                if ( v23 == GetCurrentThreadId() )
                  DebugBreak();
                v24 = *(_QWORD *)(v22 + 104);
                if ( v24 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 32LL))(v24);
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v22 + 104) + 8LL))(*(_QWORD *)(v22 + 104));
                  *(_QWORD *)(v22 + 104) = 0;
                }
                sub_18007C444(v22);
                if ( !*(_DWORD *)(v22 + 120) )
                  sub_18007C0F0(v22, 0, 4098, 0);
                sub_18007B858((LPVOID)v22);
                v4 = 0;
                goto LABEL_118;
              }
              v13 = v12 - 1;
              if ( v13 )
              {
                if ( v13 == 1 )
                {
                  v14 = (void *)*((_QWORD *)lpMem + 1);
                  if ( !v14 )
                  {
                    v15 = off_18019DE80;
                    if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
                      goto LABEL_21;
                    v16 = 25;
                    v17 = qword_180145AE8;
LABEL_20:
                    sub_180073384(*((_QWORD *)v15 + 2), v16, v17, a4);
                    v15 = off_18019DE80;
LABEL_21:
                    v4 = -2147024809;
                    goto LABEL_119;
                  }
                  v18 = sub_1800843A8(v14);
                  v4 = v18;
                  if ( v18 >= 0 )
                    goto LABEL_118;
                  v15 = off_18019DE80;
                  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
                  {
                    v19 = 26;
                    v20 = qword_180145AE8;
LABEL_117:
                    sub_1800733A8(*((_QWORD *)v15 + 2), v19, v20, (unsigned int)v18);
                    goto LABEL_118;
                  }
                  goto LABEL_119;
                }
LABEL_72:
                v15 = off_18019DE80;
                v4 = -2147024809;
LABEL_120:
                if ( v15 != (_BYTE *)&off_18019DE80 && (v15[28] & 1) != 0 )
                  sub_18007AEE8(*((_QWORD *)v15 + 2), 30, &MessageGuid, *lpMem, v4);
                goto LABEL_123;
              }
              v21 = (void *)*((_QWORD *)lpMem + 1);
              v15 = off_18019DE80;
              if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
              {
                sub_180073384(*((_QWORD *)off_18019DE80 + 2), 62, qword_180145AA8, a4);
                v15 = off_18019DE80;
              }
              if ( !v21 )
              {
                if ( v15 == (_BYTE *)&off_18019DE80 || (v15[28] & 1) == 0 )
                  goto LABEL_21;
                v16 = 63;
                goto LABEL_33;
              }
              v18 = sub_18007ECD8(v21);
              v4 = v18;
              if ( v18 < 0 )
              {
                v15 = off_18019DE80;
                if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
                  goto LABEL_119;
                v19 = 64;
                goto LABEL_116;
              }
              goto LABEL_118;
            }
            v25 = (volatile signed __int32 *)*((_QWORD *)lpMem + 1);
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 24LL))(v25);
            goto LABEL_50;
          }
          v26 = sub_180081B54(*((LPVOID *)lpMem + 1));
        }
        else
        {
          v26 = sub_18007E7BC(*((LPVOID *)lpMem + 1));
        }
      }
      else
      {
        v26 = MpClose(*((LPVOID *)lpMem + 1));
      }
    }
    v4 = v26;
    goto LABEL_118;
  }
  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
    sub_180073384(*((_QWORD *)off_18019DE80 + 2), 29, &MessageGuid, a4);
  return 1;
}

```

## disassembly

```asm
0x180078e00  mov     [rsp+arg_8], rbx
0x180078e05  mov     [rsp+arg_10], rbp
0x180078e0a  push    rsi
0x180078e0b  push    rdi
0x180078e0c  push    r14
0x180078e0e  sub     rsp, 30h
0x180078e12  xor     ebx, ebx
0x180078e14  mov     r14, rcx
0x180078e17  test    rcx, rcx
0x180078e1a  jnz     short loc_180078E52
0x180078e1c  lea     edi, [rcx+1]
0x180078e1f  mov     rcx, cs:off_18019DE80
0x180078e26  lea     rsi, off_18019DE80
0x180078e2d  cmp     rcx, rsi
0x180078e30  jz      short loc_180078E4B
0x180078e32  test    [rcx+1Ch], dil
0x180078e36  jz      short loc_180078E4B
0x180078e38  mov     rcx, [rcx+10h]
0x180078e3c  lea     edx, [rbx+1Dh]
0x180078e3f  lea     r8, MessageGuid
0x180078e46  call    sub_180073384
0x180078e4b  mov     eax, edi
0x180078e4d  jmp     loc_1800793E4
0x180078e52  mov     ecx, [rcx]
0x180078e54  lea     rsi, off_18019DE80
0x180078e5b  mov     edi, 1
0x180078e60  cmp     ecx, 8
0x180078e63  jg      loc_180079131
0x180078e69  jz      loc_1800790C3
0x180078e6f  test    ecx, ecx
0x180078e71  jz      loc_1800793DA
0x180078e77  sub     ecx, edi
0x180078e79  jz      loc_1800790B8
0x180078e7f  sub     ecx, edi
0x180078e81  jz      loc_1800790AD
0x180078e87  sub     ecx, edi
0x180078e89  jz      loc_18007909D
0x180078e8f  sub     ecx, edi
0x180078e91  jz      loc_180079062
0x180078e97  sub     ecx, edi
0x180078e99  jz      loc_180078FB6
0x180078e9f  sub     ecx, edi
0x180078ea1  jz      loc_180078F28
0x180078ea7  cmp     ecx, edi
0x180078ea9  jnz     loc_18007915E
0x180078eaf  mov     rcx, [r14+8]; lpMem
0x180078eb3  test    rcx, rcx
0x180078eb6  jnz     short loc_180078EEE
0x180078eb8  mov     rcx, cs:off_18019DE80
0x180078ebf  cmp     rcx, rsi
0x180078ec2  jz      short loc_180078EE4
0x180078ec4  test    [rcx+1Ch], dil
0x180078ec8  jz      short loc_180078EE4
0x180078eca  lea     edx, [rdi+18h]
0x180078ecd  lea     r8, qword_180145AE8
0x180078ed4  mov     rcx, [rcx+10h]
0x180078ed8  call    sub_180073384
0x180078edd  mov     rcx, cs:off_18019DE80
0x180078ee4  mov     ebx, 80070057h
0x180078ee9  jmp     loc_1800793AF
0x180078eee  call    sub_1800843A8
0x180078ef3  mov     ebx, eax
0x180078ef5  test    eax, eax
0x180078ef7  jns     loc_1800793A8
0x180078efd  mov     rcx, cs:off_18019DE80
0x180078f04  cmp     rcx, rsi
0x180078f07  jz      loc_1800793AF
0x180078f0d  test    [rcx+1Ch], dil
0x180078f11  jz      loc_1800793AF
0x180078f17  mov     edx, 1Ah
0x180078f1c  lea     r8, qword_180145AE8
0x180078f23  jmp     loc_18007939C
0x180078f28  mov     rbx, [r14+8]
0x180078f2c  mov     rcx, cs:off_18019DE80
0x180078f33  lea     rbp, qword_180145AA8
0x180078f3a  cmp     rcx, rsi
0x180078f3d  jz      short loc_180078F5D
0x180078f3f  test    byte ptr [rcx+1Ch], 4
0x180078f43  jz      short loc_180078F5D
0x180078f45  mov     rcx, [rcx+10h]
0x180078f49  mov     edx, 3Eh ; '>'
0x180078f4e  mov     r8, rbp
0x180078f51  call    sub_180073384
0x180078f56  mov     rcx, cs:off_18019DE80
0x180078f5d  test    rbx, rbx
0x180078f60  jnz     short loc_180078F80
0x180078f62  cmp     rcx, rsi
0x180078f65  jz      loc_180078EE4
0x180078f6b  test    [rcx+1Ch], dil
0x180078f6f  jz      loc_180078EE4
0x180078f75  lea     edx, [rbx+3Fh]
0x180078f78  mov     r8, rbp
0x180078f7b  jmp     loc_180078ED4
0x180078f80  mov     rcx, rbx; lpMem
0x180078f83  call    sub_18007ECD8
0x180078f88  mov     ebx, eax
0x180078f8a  test    eax, eax
0x180078f8c  jns     loc_1800793A8
0x180078f92  mov     rcx, cs:off_18019DE80
0x180078f99  cmp     rcx, rsi
0x180078f9c  jz      loc_1800793AF
0x180078fa2  test    [rcx+1Ch], dil
0x180078fa6  jz      loc_1800793AF
0x180078fac  mov     edx, 40h ; '@'
0x180078fb1  jmp     loc_180079399
0x180078fb6  mov     rbp, [r14+8]
0x180078fba  test    rbp, rbp
0x180078fbd  jnz     short loc_180078FE8
0x180078fbf  mov     rcx, cs:off_18019DE80
0x180078fc6  cmp     rcx, rsi
0x180078fc9  jz      loc_180078EE4
0x180078fcf  test    [rcx+1Ch], dil
0x180078fd3  jz      loc_180078EE4
0x180078fd9  lea     edx, [rbp+11h]
0x180078fdc  lea     r8, qword_1801459D0
0x180078fe3  jmp     loc_180078ED4
0x180078fe8  mov     rcx, [rbp+58h]
0x180078fec  call    sub_18001F89C
0x180078ff1  mov     ebx, [rbp+60h]
0x180078ff4  call    cs:GetCurrentThreadId
0x180078ffa  cmp     ebx, eax
0x180078ffc  jnz     short loc_180079003
0x180078ffe  call    DebugBreak
0x180079003  mov     rcx, [rbp+68h]
0x180079007  test    rcx, rcx
0x18007900a  jz      short loc_180079032
0x18007900c  mov     rax, [rcx]
0x18007900f  mov     rax, [rax+20h]
0x180079013  call    cs:__guard_dispatch_icall_fptr
0x180079019  mov     rcx, [rbp+68h]
0x18007901d  mov     rax, [rcx]
0x180079020  mov     rax, [rax+8]
0x180079024  call    cs:__guard_dispatch_icall_fptr
0x18007902a  mov     qword ptr [rbp+68h], 0
0x180079032  mov     rcx, rbp
0x180079035  call    sub_18007C444
0x18007903a  cmp     dword ptr [rbp+78h], 0
0x18007903e  jnz     short loc_180079053
0x180079040  xor     r9d, r9d
0x180079043  xor     edx, edx
0x180079045  mov     r8d, 1002h
0x18007904b  mov     rcx, rbp
0x18007904e  call    sub_18007C0F0
0x180079053  mov     rcx, rbp; lpMem
0x180079056  call    sub_18007B858
0x18007905b  xor     ebx, ebx
0x18007905d  jmp     loc_1800793A8
0x180079062  mov     rbx, [r14+8]
0x180079066  mov     rcx, rbx
0x180079069  mov     rax, [rbx]
0x18007906c  mov     rax, [rax+18h]
0x180079070  call    cs:__guard_dispatch_icall_fptr
0x180079076  or      eax, 0FFFFFFFFh
0x180079079  lock xadd [rbx+8], eax
0x18007907e  sub     eax, edi
0x180079080  jg      short loc_180079096
0x180079082  lfence
0x180079085  mov     rax, [rbx]
0x180079088  mov     edx, edi
0x18007908a  mov     rcx, rbx
0x18007908d  mov     rax, [rax]
0x180079090  call    cs:__guard_dispatch_icall_fptr
0x180079096  xor     ebx, ebx
0x180079098  jmp     loc_1800793DA
0x18007909d  mov     rcx, [r14+8]; lpMem
0x1800790a1  call    sub_180081B54
0x1800790a6  mov     ebx, eax
0x1800790a8  jmp     loc_1800793A8
0x1800790ad  mov     rcx, [r14+8]; lpMem
0x1800790b1  call    sub_18007E7BC
0x1800790b6  jmp     short loc_1800790A6
0x1800790b8  mov     rcx, [r14+8]; lpMem
0x1800790bc  call    MpClose
0x1800790c1  jmp     short loc_1800790A6
0x1800790c3  mov     rcx, [r14+8]; lpMem
0x1800790c7  test    rcx, rcx
0x1800790ca  jnz     short loc_1800790F7
0x1800790cc  mov     rcx, cs:off_18019DE80
0x1800790d3  cmp     rcx, rsi
0x1800790d6  jz      loc_180078EE4
0x1800790dc  test    [rcx+1Ch], dil
0x1800790e0  jz      loc_180078EE4
0x1800790e6  mov     edx, 25h ; '%'
0x1800790eb  lea     r8, qword_180145AD8
0x1800790f2  jmp     loc_180078ED4
0x1800790f7  call    sub_180082974
0x1800790fc  mov     ebx, eax
0x1800790fe  test    eax, eax
0x180079100  jns     loc_1800793A8
0x180079106  mov     rcx, cs:off_18019DE80
0x18007910d  cmp     rcx, rsi
0x180079110  jz      loc_1800793AF
0x180079116  test    [rcx+1Ch], dil
0x18007911a  jz      loc_1800793AF
0x180079120  mov     edx, 26h ; '&'
0x180079125  lea     r8, qword_180145AD8
0x18007912c  jmp     loc_18007939C
0x180079131  sub     ecx, 9
0x180079134  jz      loc_18007931F
0x18007913a  sub     ecx, edi
0x18007913c  jz      loc_1800792B4
0x180079142  sub     ecx, edi
0x180079144  jz      loc_18007923A
0x18007914a  sub     ecx, edi
0x18007914c  jz      loc_18007922C
0x180079152  sub     ecx, edi
0x180079154  jz      short loc_1800791BE
0x180079156  sub     ecx, edi
0x180079158  jz      short loc_1800791B0
0x18007915a  cmp     ecx, edi
0x18007915c  jz      short loc_18007916F
0x18007915e  mov     rcx, cs:off_18019DE80
0x180079165  mov     ebx, 80070057h
0x18007916a  jmp     loc_1800793B3
0x18007916f  mov     rbx, [r14+8]
0x180079173  mov     rcx, cs:off_18019DE80
0x18007917a  cmp     rcx, rsi
0x18007917d  jz      short loc_18007919A
0x18007917f  test    byte ptr [rcx+1Ch], 10h
0x180079183  jz      short loc_18007919A
0x180079185  mov     rcx, [rcx+10h]
0x180079189  lea     r8, qword_180147848
0x180079190  mov     edx, 18h
0x180079195  call    sub_180073384
0x18007919a  mov     rcx, rbx
0x18007919d  call    sub_1800BA688
0x1800791a2  test    rbx, rbx
0x1800791a5  jz      loc_180079096
0x1800791ab  jmp     loc_180079076
0x1800791b0  mov     rbx, [r14+8]
0x1800791b4  mov     rcx, rbx
0x1800791b7  call    sub_1800B6978
0x1800791bc  jmp     short loc_1800791A2
0x1800791be  mov     rcx, [r14+8]; lpMem
0x1800791c2  test    rcx, rcx
0x1800791c5  jnz     short loc_1800791F2
0x1800791c7  mov     rcx, cs:off_18019DE80
0x1800791ce  cmp     rcx, rsi
0x1800791d1  jz      loc_180078EE4
0x1800791d7  test    [rcx+1Ch], dil
0x1800791db  jz      loc_180078EE4
0x1800791e1  mov     edx, 27h ; '''
0x1800791e6  lea     r8, qword_180145AF8
0x1800791ed  jmp     loc_180078ED4
0x1800791f2  call    sub_180084FF8
0x1800791f7  mov     ebx, eax
0x1800791f9  test    eax, eax
0x1800791fb  jns     loc_1800793A8
0x180079201  mov     rcx, cs:off_18019DE80
0x180079208  cmp     rcx, rsi
0x18007920b  jz      loc_1800793AF
0x180079211  test    [rcx+1Ch], dil
0x180079215  jz      loc_1800793AF
0x18007921b  mov     edx, 28h ; '('
0x180079220  lea     r8, qword_180145AF8
0x180079227  jmp     loc_18007939C
0x18007922c  mov     rcx, [r14+8]; lpMem
0x180079230  call    sub_1800AD764
0x180079235  jmp     loc_1800790A6
0x18007923a  mov     rcx, [r14+8]; lpMem
0x18007923e  test    rcx, rcx
0x180079241  jnz     short loc_18007926E
0x180079243  mov     rcx, cs:off_18019DE80
0x18007924a  cmp     rcx, rsi
0x18007924d  jz      loc_180078EE4
0x180079253  test    [rcx+1Ch], dil
0x180079257  jz      loc_180078EE4
0x18007925d  mov     edx, 1Dh
0x180079262  lea     r8, qword_180146840
0x180079269  jmp     loc_180078ED4
0x18007926e  call    sub_18008F610
0x180079273  mov     ebx, eax
0x180079275  test    eax, eax
0x180079277  jns     loc_1800793A8
0x18007927d  mov     rcx, cs:off_18019DE80
0x180079284  cmp     rcx, rsi
0x180079287  jz      loc_1800793AF
0x18007928d  test    [rcx+1Ch], dil
0x180079291  jz      loc_1800793AF
0x180079297  mov     rcx, [rcx+10h]
0x18007929b  lea     r8, qword_180146840
0x1800792a2  mov     edx, 1Eh
0x1800792a7  mov     r9d, eax
0x1800792aa  call    sub_1800733A8
0x1800792af  jmp     loc_1800793A8
0x1800792b4  mov     rcx, [r14+8]; lpMem
0x1800792b8  test    rcx, rcx
0x1800792bb  jnz     short loc_1800792E8
0x1800792bd  mov     rcx, cs:off_18019DE80
0x1800792c4  cmp     rcx, rsi
0x1800792c7  jz      loc_180078EE4
0x1800792cd  test    [rcx+1Ch], dil
0x1800792d1  jz      loc_180078EE4
0x1800792d7  mov     edx, 1Bh
0x1800792dc  lea     r8, qword_180145AB8
0x1800792e3  jmp     loc_180078ED4
0x1800792e8  call    sub_1800804D8
0x1800792ed  mov     ebx, eax
0x1800792ef  test    eax, eax
0x1800792f1  jns     loc_1800793A8
  ... truncated ...
```
