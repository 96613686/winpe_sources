# CMpeg2DemuxMediaSeekingCOM::SetPositions(__int64 *,ulong,__int64 *,ulong)

- ea: `0x180024c50`
- end: `0x180024ec5`
- name: `?SetPositions@CMpeg2DemuxMediaSeekingCOM@@UEAAJPEA_JK0K@Z`
- size: `629`
- prototype: `__int64 __fastcall(CMpeg2DemuxMediaSeekingCOM *__hidden this, __int64 *, unsigned int, __int64 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800249fc`
- `0x180024b28`
- `0x180024c50`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180024e9d`
- `KERNEL32!LeaveCriticalSection` at `0x180024e9d`
- `KERNEL32!EnterCriticalSection` at `0x180024d86`
- `KERNEL32!EnterCriticalSection` at `0x180024d86`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCOM::SetPositions(
        CMpeg2DemuxMediaSeekingCOM *this,
        __int64 *a2,
        char a3,
        __int64 *a4,
        char a5)
{
  __int64 v5; // rax
  __int64 v10; // rax
  __int64 result; // rax
  __int64 v12; // r8
  int v13; // ebx
  __int64 v14; // rax
  int v15; // esi
  __int64 v16; // rdx
  int v17; // ebx
  CMpeg2DemuxMediaSeekingCore *v18; // rcx
  __int64 v19; // rax
  __int64 *v20; // r8
  int v21; // eax
  __int64 v22; // [rsp+20h] [rbp-20h] BYREF
  __int64 v23; // [rsp+28h] [rbp-18h] BYREF
  __int64 v24; // [rsp+30h] [rbp-10h] BYREF
  __int64 v25; // [rsp+70h] [rbp+30h] BYREF

  v5 = *((_QWORD *)this + 6);
  v22 = 0;
  v25 = 0;
  v23 = 0;
  v10 = *(_QWORD *)(*(_QWORD *)(v5 + 40) + 336LL);
  if ( !v10 || !*(_DWORD *)(v10 + 176) )
    return 2147549183LL;
  result = (*(__int64 (__fastcall **)(CMpeg2DemuxMediaSeekingCOM *, __int64 *))(*(_QWORD *)this + 80LL))(this, &v23);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(CMpeg2DemuxMediaSeekingCOM *, __int64 *))(*(_QWORD *)this + 88LL))(this, &v25);
    if ( (int)result >= 0 )
    {
      result = (*(__int64 (__fastcall **)(CMpeg2DemuxMediaSeekingCOM *, __int64 *))(*(_QWORD *)this + 96LL))(this, &v22);
      if ( (int)result >= 0 )
      {
        v12 = v23;
        v13 = a3 & 3;
        if ( (a3 & 3) != 0 )
        {
          if ( !a2 )
            return 2147500035LL;
          if ( (a3 & 3) != 0 )
          {
            if ( v13 == 1 )
            {
              v14 = v23;
              if ( *a2 < v23 )
                v14 = *a2;
              v22 = v14;
            }
            else
            {
              if ( v13 != 2 )
                return 2147942487LL;
              v22 += *a2;
            }
          }
        }
        v15 = a5 & 3;
        if ( (a5 & 3) == 0 )
          goto LABEL_37;
        if ( !a4 )
          return 2147500035LL;
        if ( (a5 & 3) != 0 )
        {
          if ( v15 == 1 )
          {
            if ( *a4 < v23 )
              v12 = *a4;
            goto LABEL_27;
          }
          if ( v15 == 2 )
          {
            v16 = v25 + *a4;
LABEL_25:
            if ( v16 < v23 )
              v12 = v16;
LABEL_27:
            v25 = v12;
LABEL_28:
            EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
            if ( (a3 & 3) != 0 && (v22 < 0 || v15 && v22 > v25) )
            {
              v17 = -2147024809;
LABEL_60:
              LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
              return (unsigned int)v17;
            }
            v18 = (CMpeg2DemuxMediaSeekingCore *)*((_QWORD *)this + 6);
            if ( (a3 & 3) == 0 )
            {
              v21 = CMpeg2DemuxMediaSeekingCore::SetFileStopPosition(v18, &v25);
              goto LABEL_54;
            }
            if ( v15 )
            {
              v20 = &v25;
              goto LABEL_49;
            }
            if ( *(_QWORD *)(*((_QWORD *)v18 + 5) + 160LL) )
            {
              if ( *(_QWORD *)v18 == *(_QWORD *)&TIME_FORMAT_MEDIA_TIME.Data1
                && *((_QWORD *)v18 + 1) == *(_QWORD *)TIME_FORMAT_MEDIA_TIME.Data4 )
              {
                v19 = *((_QWORD *)v18 + 3);
LABEL_48:
                v24 = v19;
                v20 = &v24;
LABEL_49:
                v21 = CMpeg2DemuxMediaSeekingCore::SeekTo(v18, &v22, v20, 1.0);
LABEL_54:
                v17 = v21;
                goto LABEL_55;
              }
              if ( *(_QWORD *)v18 == *(_QWORD *)&TIME_FORMAT_BYTE.Data1
                && *((_QWORD *)v18 + 1) == *(_QWORD *)TIME_FORMAT_BYTE.Data4 )
              {
                v19 = *((_QWORD *)v18 + 2);
                goto LABEL_48;
              }
              v17 = -2147467259;
            }
            else
            {
              v17 = -2147418113;
            }
LABEL_55:
            if ( v17 >= 0 )
            {
              if ( (a3 & 8) == 0
                || (v17 = (*(__int64 (__fastcall **)(CMpeg2DemuxMediaSeekingCOM *, __int64 *))(*(_QWORD *)this + 96LL))(
                            this,
                            a2),
                    v17 >= 0) )
              {
                if ( (a5 & 8) != 0 )
                  v17 = (*(__int64 (__fastcall **)(CMpeg2DemuxMediaSeekingCOM *, __int64 *))(*(_QWORD *)this + 88LL))(
                          this,
                          a4);
              }
            }
            goto LABEL_60;
          }
          if ( v15 == 3 && (a3 & 3) != 0 && a2 )
          {
            v16 = *a4 + *a2;
            goto LABEL_25;
          }
        }
        else
        {
LABEL_37:
          if ( (a3 & 3) != 0 )
            goto LABEL_28;
        }
        return 2147942487LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024c50  mov     [rsp-28h+arg_8], rbx
0x180024c55  mov     [rsp-28h+arg_10], rsi
0x180024c5a  push    rbp
0x180024c5b  push    rdi
0x180024c5c  push    r12
0x180024c5e  push    r14
0x180024c60  push    r15
0x180024c62  mov     rbp, rsp
0x180024c65  sub     rsp, 40h
0x180024c69  mov     rax, [rcx+30h]
0x180024c6d  mov     r15, r9
0x180024c70  mov     [rbp+var_20], 0
0x180024c78  mov     r12d, r8d
0x180024c7b  mov     [rbp+arg_0], 0
0x180024c83  mov     r14, rdx
0x180024c86  mov     [rbp+var_18], 0
0x180024c8e  mov     rdi, rcx
0x180024c91  mov     r10, [rax+28h]
0x180024c95  mov     rax, [r10+150h]
0x180024c9c  test    rax, rax
0x180024c9f  jz      loc_180024EA7
0x180024ca5  cmp     dword ptr [rax+0B0h], 0
0x180024cac  jz      loc_180024EA7
0x180024cb2  mov     rax, [rcx]
0x180024cb5  lea     rdx, [rbp+var_18]
0x180024cb9  mov     rax, [rax+50h]
0x180024cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cc2  test    eax, eax
0x180024cc4  js      loc_180024EAC
0x180024cca  mov     rax, [rdi]
0x180024ccd  lea     rdx, [rbp+arg_0]
0x180024cd1  mov     rcx, rdi
0x180024cd4  mov     rax, [rax+58h]
0x180024cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cdd  test    eax, eax
0x180024cdf  js      loc_180024EAC
0x180024ce5  mov     rax, [rdi]
0x180024ce8  lea     rdx, [rbp+var_20]
0x180024cec  mov     rcx, rdi
0x180024cef  mov     rax, [rax+60h]
0x180024cf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cf8  test    eax, eax
0x180024cfa  js      loc_180024EAC
0x180024d00  mov     r8, [rbp+var_18]
0x180024d04  mov     ebx, r12d
0x180024d07  and     ebx, 3
0x180024d0a  jz      short loc_180024D3C
0x180024d0c  test    r14, r14
0x180024d0f  jz      short loc_180024D49
0x180024d11  mov     eax, ebx
0x180024d13  test    ebx, ebx
0x180024d15  jz      short loc_180024D3C
0x180024d17  sub     eax, 1
0x180024d1a  jz      short loc_180024D2E
0x180024d1c  cmp     eax, 1
0x180024d1f  jnz     loc_180024DC3
0x180024d25  mov     rax, [r14]
0x180024d28  add     [rbp+var_20], rax
0x180024d2c  jmp     short loc_180024D3C
0x180024d2e  cmp     [r14], r8
0x180024d31  mov     rax, r8
0x180024d34  cmovl   rax, [r14]
0x180024d38  mov     [rbp+var_20], rax
0x180024d3c  mov     esi, [rbp+arg_20]
0x180024d3f  and     esi, 3
0x180024d42  jz      short loc_180024DBF
0x180024d44  test    r15, r15
0x180024d47  jnz     short loc_180024D53
0x180024d49  mov     eax, 80004003h
0x180024d4e  jmp     loc_180024EAC
0x180024d53  mov     eax, esi
0x180024d55  test    esi, esi
0x180024d57  jz      short loc_180024DBF
0x180024d59  sub     eax, 1
0x180024d5c  jz      short loc_180024DB6
0x180024d5e  sub     eax, 1
0x180024d61  jz      short loc_180024DAD
0x180024d63  cmp     eax, 1
0x180024d66  jnz     short loc_180024DC3
0x180024d68  test    ebx, ebx
0x180024d6a  jz      short loc_180024DC3
0x180024d6c  test    r14, r14
0x180024d6f  jz      short loc_180024DC3
0x180024d71  mov     rdx, [r14]
0x180024d74  add     rdx, [r15]
0x180024d77  cmp     rdx, r8
0x180024d7a  cmovl   r8, rdx
0x180024d7e  mov     [rbp+arg_0], r8
0x180024d82  mov     rcx, [rdi+28h]; lpCriticalSection
0x180024d86  call    cs:__imp_EnterCriticalSection
0x180024d8c  test    ebx, ebx
0x180024d8e  jz      short loc_180024DCD
0x180024d90  mov     rax, [rbp+var_20]
0x180024d94  test    rax, rax
0x180024d97  js      short loc_180024DA3
0x180024d99  test    esi, esi
0x180024d9b  jz      short loc_180024DCD
0x180024d9d  cmp     rax, [rbp+arg_0]
0x180024da1  jle     short loc_180024DCD
0x180024da3  mov     ebx, 80070057h
0x180024da8  jmp     loc_180024E99
0x180024dad  mov     rdx, [r15]
0x180024db0  add     rdx, [rbp+arg_0]
0x180024db4  jmp     short loc_180024D77
0x180024db6  cmp     [r15], r8
0x180024db9  cmovl   r8, [r15]
0x180024dbd  jmp     short loc_180024D7E
0x180024dbf  test    ebx, ebx
0x180024dc1  jnz     short loc_180024D82
0x180024dc3  mov     eax, 80070057h
0x180024dc8  jmp     loc_180024EAC
0x180024dcd  mov     rcx, [rdi+30h]; this
0x180024dd1  test    ebx, ebx
0x180024dd3  jz      short loc_180024E52
0x180024dd5  test    esi, esi
0x180024dd7  jnz     short loc_180024E4C
0x180024dd9  mov     rax, [rcx+28h]
0x180024ddd  cmp     qword ptr [rax+0A0h], 0
0x180024de5  jz      short loc_180024E45
0x180024de7  mov     rax, [rcx]
0x180024dea  cmp     rax, qword ptr cs:TIME_FORMAT_MEDIA_TIME.Data1
0x180024df1  jnz     short loc_180024E06
0x180024df3  mov     rax, [rcx+8]
0x180024df7  cmp     rax, qword ptr cs:TIME_FORMAT_MEDIA_TIME.Data4
0x180024dfe  jnz     short loc_180024E06
0x180024e00  mov     rax, [rcx+18h]
0x180024e04  jmp     short loc_180024E23
0x180024e06  mov     rax, [rcx]
0x180024e09  cmp     rax, qword ptr cs:TIME_FORMAT_BYTE.Data1
0x180024e10  jnz     short loc_180024E3E
0x180024e12  mov     rax, [rcx+8]
0x180024e16  cmp     rax, qword ptr cs:TIME_FORMAT_BYTE.Data4
0x180024e1d  jnz     short loc_180024E3E
0x180024e1f  mov     rax, [rcx+10h]
0x180024e23  mov     [rbp+var_10], rax
0x180024e27  lea     r8, [rbp+var_10]; __int64 *
0x180024e2b  movsd   xmm3, cs:__real@3ff0000000000000; double
0x180024e33  lea     rdx, [rbp+var_20]; __int64 *
0x180024e37  call    ?SeekTo@CMpeg2DemuxMediaSeekingCore@@QEAAJPEA_J0N@Z; CMpeg2DemuxMediaSeekingCore::SeekTo(__int64 *,__int64 *,double)
0x180024e3c  jmp     short loc_180024E5B
0x180024e3e  mov     ebx, 80004005h
0x180024e43  jmp     short loc_180024E5D
0x180024e45  mov     ebx, 8000FFFFh
0x180024e4a  jmp     short loc_180024E5D
0x180024e4c  lea     r8, [rbp+arg_0]
0x180024e50  jmp     short loc_180024E2B
0x180024e52  lea     rdx, [rbp+arg_0]; __int64 *
0x180024e56  call    ?SetFileStopPosition@CMpeg2DemuxMediaSeekingCore@@QEAAJPEA_J@Z; CMpeg2DemuxMediaSeekingCore::SetFileStopPosition(__int64 *)
0x180024e5b  mov     ebx, eax
0x180024e5d  test    ebx, ebx
0x180024e5f  js      short loc_180024E99
0x180024e61  test    r12b, 8
0x180024e65  jz      short loc_180024E7F
0x180024e67  mov     rax, [rdi]
0x180024e6a  mov     rdx, r14
0x180024e6d  mov     rcx, rdi
0x180024e70  mov     rax, [rax+60h]
0x180024e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e79  mov     ebx, eax
0x180024e7b  test    eax, eax
0x180024e7d  js      short loc_180024E99
0x180024e7f  test    byte ptr [rbp+arg_20], 8
0x180024e83  jz      short loc_180024E99
0x180024e85  mov     rax, [rdi]
0x180024e88  mov     rdx, r15
0x180024e8b  mov     rcx, rdi
0x180024e8e  mov     rax, [rax+58h]
0x180024e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e97  mov     ebx, eax
0x180024e99  mov     rcx, [rdi+28h]; lpCriticalSection
0x180024e9d  call    cs:__imp_LeaveCriticalSection
0x180024ea3  mov     eax, ebx
0x180024ea5  jmp     short loc_180024EAC
0x180024ea7  mov     eax, 8000FFFFh
0x180024eac  lea     r11, [rsp+40h+var_s0]
0x180024eb1  mov     rbx, [r11+38h]
0x180024eb5  mov     rsi, [r11+40h]
0x180024eb9  mov     rsp, r11
0x180024ebc  pop     r15
0x180024ebe  pop     r14
0x180024ec0  pop     r12
0x180024ec2  pop     rdi
0x180024ec3  pop     rbp
0x180024ec4  retn
```
