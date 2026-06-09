# DetourTransactionCommitEx(x)

- ea: `0x40de00`
- end: `0x40e272`
- name: `_DetourTransactionCommitEx@4`
- size: `1138`
- prototype: `int __stdcall(_DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x40ddf0`

## callees

- `0x40cb60`
- `0x40d7f0`
- `0x40de00`
- `0x40eb05`
- `0x40eb1b`
- `0x40eb27`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x40de2a`
- `KERNEL32!GetCurrentThreadId` at `0x40de63`
- `KERNEL32!GetCurrentThreadId` at `0x40de2a`
- `KERNEL32!GetCurrentThreadId` at `0x40de63`
- `KERNEL32!GetCurrentProcess` at `0x40e0b4`
- `KERNEL32!GetCurrentProcess` at `0x40e1d2`
- `KERNEL32!GetCurrentProcess` at `0x40e0b4`
- `KERNEL32!GetCurrentProcess` at `0x40e1d2`
- `KERNEL32!ResumeThread` at `0x40defa`
- `KERNEL32!ResumeThread` at `0x40e218`
- `KERNEL32!ResumeThread` at `0x40defa`
- `KERNEL32!ResumeThread` at `0x40e218`
- `KERNEL32!VirtualFree` at `0x40e1bc`
- `KERNEL32!VirtualFree` at `0x40e1bc`
- `KERNEL32!VirtualProtect` at `0x40de93`
- `KERNEL32!VirtualProtect` at `0x40e0d9`
- `KERNEL32!VirtualProtect` at `0x40e1f1`
- `KERNEL32!VirtualProtect` at `0x40de93`
- `KERNEL32!VirtualProtect` at `0x40e0d9`
- `KERNEL32!VirtualProtect` at `0x40e1f1`
- `KERNEL32!FlushInstructionCache` at `0x40e0eb`
- `KERNEL32!FlushInstructionCache` at `0x40e1fe`
- `KERNEL32!FlushInstructionCache` at `0x40e0eb`
- `KERNEL32!FlushInstructionCache` at `0x40e1fe`
- `KERNEL32!SetThreadContext` at `0x40e092`
- `KERNEL32!SetThreadContext` at `0x40e092`
- `KERNEL32!GetThreadContext` at `0x40dfd0`
- `KERNEL32!GetThreadContext` at `0x40dfd0`

## pseudocode

```c
int __stdcall DetourTransactionCommitEx(_DWORD *a1)
{
  void *v2; // edi
  unsigned int v3; // esi
  void *v4; // esi
  HANDLE *v5; // edi
  HANDLE *v6; // esi
  void *v7; // esi
  int v8; // ecx
  int v9; // eax
  int v10; // edx
  int v11; // ecx
  void *v12; // edx
  int v13; // eax
  size_t v14; // ecx
  HANDLE *v15; // ebp
  _DWORD *v16; // esi
  DWORD Eip; // ebx
  DWORD v18; // ecx
  int v19; // eax
  unsigned __int8 v20; // ch
  DWORD v21; // eax
  DWORD v22; // ecx
  int v23; // edi
  int v24; // edx
  int v25; // eax
  HANDLE CurrentProcess; // eax
  void *v27; // edi
  void *v28; // ebx
  unsigned int v29; // esi
  void *v30; // esi
  LPCVOID *v31; // edx
  LPCVOID *v32; // esi
  int v33; // ecx
  unsigned int v34; // eax
  HANDLE v35; // eax
  _DWORD *v36; // esi
  void *v37; // edi
  HANDLE *v38; // edi
  HANDLE *v39; // esi
  DWORD v40; // [esp+0h] [ebp-2DCh] BYREF
  int i; // [esp+4h] [ebp-2D8h]
  DWORD flOldProtect; // [esp+8h] [ebp-2D4h] BYREF
  CONTEXT Context; // [esp+Ch] [ebp-2D0h] BYREF

  flOldProtect = (DWORD)a1;
  if ( a1 )
    *a1 = dword_40F484;
  if ( dword_40F47C != GetCurrentThreadId() )
    return 4317;
  if ( !dword_40F480 )
  {
    v7 = lpMem;
    for ( i = 0; v7; v7 = *(void **)v7 )
    {
      v8 = *((_DWORD *)v7 + 4);
      if ( *((_DWORD *)v7 + 1) )
      {
        memcpy(*((void **)v7 + 3), (const void *)(v8 + 32), *(unsigned __int8 *)(v8 + 54));
        v9 = *((_DWORD *)v7 + 3);
      }
      else
      {
        v10 = *((_DWORD *)v7 + 3);
        v11 = *(_DWORD *)(v8 + 68);
        *(_BYTE *)v10 = -23;
        *(_DWORD *)(v10 + 1) = v11 - (v10 + 5);
        v12 = (void *)(v10 + 5);
        v13 = *((_DWORD *)v7 + 4);
        v14 = *(_DWORD *)(v13 + 64) - (_DWORD)v12;
        if ( (unsigned int)v12 > *(_DWORD *)(v13 + 64) )
          v14 = 0;
        if ( v14 )
          memset(v12, 204, v14);
        v9 = *((_DWORD *)v7 + 4);
      }
      **((_DWORD **)v7 + 2) = v9;
    }
    v15 = (HANDLE *)dword_40F488;
    if ( !dword_40F488 )
    {
LABEL_47:
      CurrentProcess = GetCurrentProcess();
      v27 = lpMem;
      v28 = CurrentProcess;
      if ( lpMem )
      {
        do
        {
          VirtualProtect(
            *((LPVOID *)v27 + 3),
            *(unsigned __int8 *)(*((_DWORD *)v27 + 4) + 54),
            *((_DWORD *)v27 + 5),
            &v40);
          FlushInstructionCache(v28, *((LPCVOID *)v27 + 3), *(unsigned __int8 *)(*((_DWORD *)v27 + 4) + 54));
          if ( *((_DWORD *)v27 + 1) )
          {
            v29 = *((_DWORD *)v27 + 4);
            if ( v29 )
            {
              memset((void *)v29, 0, 0x48u);
              i = 1;
              *(_DWORD *)(v29 + 64) = *(_DWORD *)((v29 & 0xFFFF0000) + 8);
              *(_DWORD *)((v29 & 0xFFFF0000) + 8) = v29;
              *((_DWORD *)v27 + 4) = 0;
            }
          }
          v30 = *(void **)v27;
          operator delete(v27);
          v27 = v30;
        }
        while ( v30 );
      }
      lpMem = 0;
      if ( i )
      {
        if ( !dword_40F478 )
        {
          v31 = (LPCVOID *)lpBaseAddress;
          v32 = &lpBaseAddress;
          if ( lpBaseAddress )
          {
            do
            {
              if ( *v31 == (LPCVOID)1383232612 )
              {
                v33 = 0;
                while ( 1 )
                {
                  v34 = (unsigned int)v31[18 * v33 + 34];
                  if ( v34 )
                  {
                    if ( v34 < (unsigned int)v31 || v34 >= (unsigned int)(v31 + 0x4000) )
                      break;
                  }
                  if ( (unsigned int)++v33 >= 0x38D )
                  {
                    *v32 = v31[1];
                    VirtualFree(v31, 0, 0x8000u);
                    dword_40F470 = 0;
                    goto LABEL_63;
                  }
                }
              }
              v32 = v31 + 1;
LABEL_63:
              v31 = (LPCVOID *)*v32;
            }
            while ( *v32 );
          }
        }
      }
      v35 = GetCurrentProcess();
      v36 = lpBaseAddress;
      v37 = v35;
      if ( lpBaseAddress )
      {
        do
        {
          VirtualProtect(v36, 0x10000u, 0x20u, &v40);
          FlushInstructionCache(v37, v36, 0x10000u);
          v36 = (_DWORD *)v36[1];
        }
        while ( v36 );
      }
      v38 = (HANDLE *)dword_40F488;
      if ( dword_40F488 )
      {
        do
        {
          ResumeThread(v38[1]);
          v39 = (HANDLE *)*v38;
          operator delete(v38);
          v38 = v39;
        }
        while ( v39 );
      }
      dword_40F488 = 0;
      dword_40F47C = 0;
      if ( flOldProtect )
        *(_DWORD *)flOldProtect = dword_40F484;
      return dword_40F480;
    }
    while ( 1 )
    {
      Context.ContextFlags = 65537;
      if ( GetThreadContext(v15[1], &Context) )
      {
        v16 = lpMem;
        if ( lpMem )
          break;
      }
LABEL_46:
      v15 = (HANDLE *)*v15;
      if ( !v15 )
        goto LABEL_47;
    }
    Eip = Context.Eip;
    while ( 1 )
    {
      if ( v16[1] )
      {
        v18 = v16[4];
        v40 = v18;
        if ( Eip < v18 || Eip >= v18 + 4 )
          goto LABEL_45;
        v19 = 0;
        while ( 1 )
        {
          v20 = *(_BYTE *)(v18 + v19 + 56);
          if ( v20 >> 3 == (_BYTE)Eip - *((_BYTE *)v16 + 16) )
            break;
          v18 = v40;
          if ( (unsigned int)++v19 >= 8 )
          {
            v21 = v16[3];
            goto LABEL_44;
          }
        }
        v21 = v16[3] + (v20 & 7);
      }
      else
      {
        v22 = v16[3];
        if ( Eip < v22 )
          goto LABEL_45;
        v23 = v16[4];
        if ( Eip >= v22 + *(unsigned __int8 *)(v23 + 54) )
          goto LABEL_45;
        v24 = 0;
        while ( (*(_BYTE *)(v23 + v24 + 56) & 7) != (_BYTE)Eip - *((_BYTE *)v16 + 12) )
        {
          if ( (unsigned int)++v24 >= 8 )
          {
            v25 = 0;
            goto LABEL_43;
          }
        }
        v25 = *(unsigned __int8 *)(v23 + v24 + 56) >> 3;
LABEL_43:
        v21 = v23 + v25;
      }
LABEL_44:
      Context.Eip = v21;
      SetThreadContext(v15[1], &Context);
      Eip = Context.Eip;
LABEL_45:
      v16 = (_DWORD *)*v16;
      if ( !v16 )
        goto LABEL_46;
    }
  }
  if ( dword_40F47C == GetCurrentThreadId() )
  {
    v2 = lpMem;
    if ( lpMem )
    {
      do
      {
        VirtualProtect(
          *((LPVOID *)v2 + 3),
          *(unsigned __int8 *)(*((_DWORD *)v2 + 4) + 54),
          *((_DWORD *)v2 + 5),
          &flOldProtect);
        if ( !*((_DWORD *)v2 + 1) )
        {
          v3 = *((_DWORD *)v2 + 4);
          if ( v3 )
          {
            memset((void *)v3, 0, 0x48u);
            *(_DWORD *)(v3 + 64) = *(_DWORD *)((v3 & 0xFFFF0000) + 8);
            *(_DWORD *)((v3 & 0xFFFF0000) + 8) = v3;
            *((_DWORD *)v2 + 4) = 0;
          }
        }
        v4 = *(void **)v2;
        operator delete(v2);
        v2 = v4;
      }
      while ( v4 );
    }
    lpMem = 0;
    detour_runnable_trampoline_regions();
    v5 = (HANDLE *)dword_40F488;
    if ( dword_40F488 )
    {
      do
      {
        ResumeThread(v5[1]);
        v6 = (HANDLE *)*v5;
        operator delete(v5);
        v5 = v6;
      }
      while ( v6 );
    }
    dword_40F488 = 0;
    dword_40F47C = 0;
  }
  return dword_40F480;
}

```

## disassembly

```asm
0x40de00  sub     esp, 2DCh
0x40de06  mov     eax, ___security_cookie
0x40de0b  xor     eax, esp
0x40de0d  mov     [esp+2DCh+var_4], eax
0x40de14  mov     ecx, [esp+2DCh+arg_0]
0x40de1b  mov     [esp+2DCh+flOldProtect], ecx
0x40de1f  test    ecx, ecx
0x40de21  jz      short loc_40DE2A
0x40de23  mov     eax, dword_40F484
0x40de28  mov     [ecx], eax
0x40de2a  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40de30  cmp     dword_40F47C, eax
0x40de36  jz      short loc_40DE54
0x40de38  mov     eax, 10DDh
0x40de3d  mov     ecx, [esp+2DCh+var_4]
0x40de44  xor     ecx, esp; StackCookie
0x40de46  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40de4b  add     esp, 2DCh
0x40de51  retn    4
0x40de54  cmp     dword_40F480, 0
0x40de5b  push    esi
0x40de5c  push    edi
0x40de5d  jz      loc_40DF2C
0x40de63  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40de69  cmp     dword_40F47C, eax
0x40de6f  jnz     loc_40E254
0x40de75  mov     edi, lpMem
0x40de7b  test    edi, edi
0x40de7d  jz      short loc_40DEDE
0x40de7f  nop
0x40de80  lea     eax, [esp+2E4h+flOldProtect]
0x40de84  push    eax; lpflOldProtect
0x40de85  mov     eax, [edi+10h]
0x40de88  push    dword ptr [edi+14h]; flNewProtect
0x40de8b  movzx   eax, byte ptr [eax+36h]
0x40de8f  push    eax; dwSize
0x40de90  push    dword ptr [edi+0Ch]; lpAddress
0x40de93  call    ds:__imp__VirtualProtect@16; VirtualProtect(x,x,x,x)
0x40de99  cmp     dword ptr [edi+4], 0
0x40de9d  jnz     short loc_40DECB
0x40de9f  mov     esi, [edi+10h]
0x40dea2  test    esi, esi
0x40dea4  jz      short loc_40DECB
0x40dea6  push    48h ; 'H'; Size
0x40dea8  push    0; Val
0x40deaa  push    esi; void *
0x40deab  call    _memset
0x40deb0  mov     ecx, esi
0x40deb2  add     esp, 0Ch
0x40deb5  and     ecx, 0FFFF0000h
0x40debb  mov     eax, [ecx+8]
0x40debe  mov     [esi+40h], eax
0x40dec1  mov     [ecx+8], esi
0x40dec4  mov     dword ptr [edi+10h], 0
0x40decb  mov     esi, [edi]
0x40decd  push    18h; unsigned int
0x40decf  push    edi; lpMem
0x40ded0  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x40ded5  add     esp, 8
0x40ded8  mov     edi, esi
0x40deda  test    esi, esi
0x40dedc  jnz     short loc_40DE80
0x40dede  mov     lpMem, 0
0x40dee8  call    detour_runnable_trampoline_regions
0x40deed  mov     edi, dword_40F488
0x40def3  test    edi, edi
0x40def5  jz      short loc_40DF13
0x40def7  push    dword ptr [edi+4]; hThread
0x40defa  call    ds:__imp__ResumeThread@4; ResumeThread(x)
0x40df00  mov     esi, [edi]
0x40df02  push    8; unsigned int
0x40df04  push    edi; lpMem
0x40df05  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x40df0a  add     esp, 8
0x40df0d  mov     edi, esi
0x40df0f  test    esi, esi
0x40df11  jnz     short loc_40DEF7
0x40df13  mov     dword_40F488, 0
0x40df1d  mov     dword_40F47C, 0
0x40df27  jmp     loc_40E254
0x40df2c  mov     esi, lpMem
0x40df32  mov     [esp+2E4h+var_2D8], 0
0x40df3a  test    esi, esi
0x40df3c  jz      short loc_40DFA7
0x40df3e  xchg    ax, ax
0x40df40  cmp     dword ptr [esi+4], 0
0x40df44  mov     ecx, [esi+10h]
0x40df47  jz      short loc_40DF62
0x40df49  movzx   eax, byte ptr [ecx+36h]
0x40df4d  push    eax; Size
0x40df4e  lea     eax, [ecx+20h]
0x40df51  push    eax; Src
0x40df52  push    dword ptr [esi+0Ch]; void *
0x40df55  call    _memcpy
0x40df5a  mov     eax, [esi+0Ch]
0x40df5d  add     esp, 0Ch
0x40df60  jmp     short loc_40DF9C
0x40df62  mov     edx, [esi+0Ch]
0x40df65  xor     edi, edi
0x40df67  mov     ecx, [ecx+44h]
0x40df6a  lea     eax, [edx+5]
0x40df6d  mov     byte ptr [edx], 0E9h
0x40df70  sub     ecx, eax
0x40df72  mov     [edx+1], ecx
0x40df75  add     edx, 5
0x40df78  mov     eax, [esi+10h]
0x40df7b  mov     ecx, [eax+40h]
0x40df7e  sub     ecx, edx
0x40df80  cmp     edx, [eax+40h]
0x40df83  cmova   ecx, edi
0x40df86  test    ecx, ecx
0x40df88  jz      short loc_40DF99
0x40df8a  push    ecx; Size
0x40df8b  push    0CCh; Val
0x40df90  push    edx; void *
0x40df91  call    _memset
0x40df96  add     esp, 0Ch
0x40df99  mov     eax, [esi+10h]
0x40df9c  mov     ecx, [esi+8]
0x40df9f  mov     [ecx], eax
0x40dfa1  mov     esi, [esi]
0x40dfa3  test    esi, esi
0x40dfa5  jnz     short loc_40DF40
0x40dfa7  push    ebx
0x40dfa8  push    ebp
0x40dfa9  mov     ebp, dword_40F488
0x40dfaf  test    ebp, ebp
0x40dfb1  jz      loc_40E0B4
0x40dfb7  nop     word ptr [eax+eax+00000000h]
0x40dfc0  lea     eax, [esp+2ECh+Context]
0x40dfc4  mov     [esp+2ECh+Context.ContextFlags], 10001h
0x40dfcc  push    eax; lpContext
0x40dfcd  push    dword ptr [ebp+4]; hThread
0x40dfd0  call    ds:__imp__GetThreadContext@8; GetThreadContext(x,x)
0x40dfd6  test    eax, eax
0x40dfd8  jz      loc_40E0A9
0x40dfde  mov     esi, lpMem
0x40dfe4  test    esi, esi
0x40dfe6  jz      loc_40E0A9
0x40dfec  mov     ebx, [esp+2ECh+Context.Eip]
0x40dff3  cmp     dword ptr [esi+4], 0
0x40dff7  jz      short loc_40E046
0x40dff9  mov     ecx, [esi+10h]
0x40dffc  mov     [esp+2ECh+var_2DC], ecx
0x40e000  cmp     ebx, ecx
0x40e002  jb      loc_40E09F
0x40e008  lea     eax, [ecx+4]
0x40e00b  cmp     ebx, eax
0x40e00d  jnb     loc_40E09F
0x40e013  xor     eax, eax
0x40e015  mov     ch, [ecx+eax+38h]
0x40e019  mov     dl, bl
0x40e01b  sub     dl, [esi+10h]
0x40e01e  mov     cl, ch
0x40e020  shr     cl, 3
0x40e023  cmp     cl, dl
0x40e025  jz      short loc_40E03B
0x40e027  mov     ecx, [esp+2ECh+var_2DC]
0x40e02b  inc     eax
0x40e02c  cmp     eax, 8
0x40e02f  jb      short loc_40E015
0x40e031  xor     ch, ch
0x40e033  movzx   eax, ch
0x40e036  add     eax, [esi+0Ch]
0x40e039  jmp     short loc_40E083
0x40e03b  and     ch, 7
0x40e03e  movzx   eax, ch
0x40e041  add     eax, [esi+0Ch]
0x40e044  jmp     short loc_40E083
0x40e046  mov     ecx, [esi+0Ch]
0x40e049  cmp     ebx, ecx
0x40e04b  jb      short loc_40E09F
0x40e04d  mov     edi, [esi+10h]
0x40e050  movzx   eax, byte ptr [edi+36h]
0x40e054  add     eax, ecx
0x40e056  cmp     ebx, eax
0x40e058  jnb     short loc_40E09F
0x40e05a  xor     edx, edx
0x40e05c  nop     dword ptr [eax+00h]
0x40e060  mov     ah, [edi+edx+38h]
0x40e064  mov     cl, bl
0x40e066  sub     cl, [esi+0Ch]
0x40e069  mov     al, ah
0x40e06b  and     al, 7
0x40e06d  cmp     al, cl
0x40e06f  jz      short loc_40E07B
0x40e071  inc     edx
0x40e072  cmp     edx, 8
0x40e075  jb      short loc_40E060
0x40e077  xor     eax, eax
0x40e079  jmp     short loc_40E081
0x40e07b  movzx   eax, ah
0x40e07e  shr     eax, 3
0x40e081  add     eax, edi
0x40e083  mov     [esp+2ECh+Context.Eip], eax
0x40e08a  lea     eax, [esp+2ECh+Context]
0x40e08e  push    eax; lpContext
0x40e08f  push    dword ptr [ebp+4]; hThread
0x40e092  call    ds:__imp__SetThreadContext@8; SetThreadContext(x,x)
0x40e098  mov     ebx, [esp+2ECh+Context.Eip]
0x40e09f  mov     esi, [esi]
0x40e0a1  test    esi, esi
0x40e0a3  jnz     loc_40DFF3
0x40e0a9  mov     ebp, [ebp+0]
0x40e0ac  test    ebp, ebp
0x40e0ae  jnz     loc_40DFC0
0x40e0b4  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x40e0ba  mov     edi, lpMem
0x40e0c0  mov     ebx, eax
0x40e0c2  test    edi, edi
0x40e0c4  jz      short loc_40E13E
0x40e0c6  lea     eax, [esp+2ECh+var_2DC]
0x40e0ca  push    eax; lpflOldProtect
0x40e0cb  mov     eax, [edi+10h]
0x40e0ce  push    dword ptr [edi+14h]; flNewProtect
0x40e0d1  movzx   eax, byte ptr [eax+36h]
0x40e0d5  push    eax; dwSize
0x40e0d6  push    dword ptr [edi+0Ch]; lpAddress
0x40e0d9  call    ds:__imp__VirtualProtect@16; VirtualProtect(x,x,x,x)
0x40e0df  mov     eax, [edi+10h]
0x40e0e2  movzx   eax, byte ptr [eax+36h]
0x40e0e6  push    eax; dwSize
0x40e0e7  push    dword ptr [edi+0Ch]; lpBaseAddress
0x40e0ea  push    ebx; hProcess
0x40e0eb  call    ds:__imp__FlushInstructionCache@12; FlushInstructionCache(x,x,x)
0x40e0f1  cmp     dword ptr [edi+4], 0
0x40e0f5  jz      short loc_40E12B
0x40e0f7  mov     esi, [edi+10h]
0x40e0fa  test    esi, esi
0x40e0fc  jz      short loc_40E12B
0x40e0fe  push    48h ; 'H'; Size
0x40e100  push    0; Val
0x40e102  push    esi; void *
0x40e103  call    _memset
0x40e108  mov     ecx, esi
0x40e10a  mov     [esp+2F8h+var_2D8], 1
0x40e112  add     esp, 0Ch
0x40e115  and     ecx, 0FFFF0000h
0x40e11b  mov     eax, [ecx+8]
0x40e11e  mov     [esi+40h], eax
0x40e121  mov     [ecx+8], esi
0x40e124  mov     dword ptr [edi+10h], 0
0x40e12b  mov     esi, [edi]
0x40e12d  push    18h; unsigned int
0x40e12f  push    edi; lpMem
0x40e130  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x40e135  add     esp, 8
0x40e138  mov     edi, esi
0x40e13a  test    esi, esi
0x40e13c  jnz     short loc_40E0C6
0x40e13e  cmp     [esp+2ECh+var_2D8], 0
0x40e143  pop     ebp
0x40e144  mov     lpMem, 0
0x40e14e  pop     ebx
0x40e14f  jz      loc_40E1D2
0x40e155  cmp     dword_40F478, 0
0x40e15c  jnz     short loc_40E1D2
0x40e15e  mov     edx, lpBaseAddress
0x40e164  mov     esi, offset lpBaseAddress
0x40e169  test    edx, edx
0x40e16b  jz      short loc_40E1D2
0x40e16d  nop     dword ptr [eax]
0x40e170  cmp     dword ptr [edx], 52727464h
0x40e176  jz      short loc_40E17D
0x40e178  lea     esi, [edx+4]
0x40e17b  jmp     short loc_40E1CC
0x40e17d  lea     edi, [edx+10000h]
0x40e183  xor     ecx, ecx
0x40e185  nop     word ptr [eax+eax+00000000h]
0x40e190  lea     eax, [ecx+ecx*8]
0x40e193  mov     eax, [edx+eax*8+88h]
0x40e19a  test    eax, eax
0x40e19c  jz      short loc_40E1A6
0x40e19e  cmp     eax, edx
0x40e1a0  jb      short loc_40E178
0x40e1a2  cmp     eax, edi
0x40e1a4  jnb     short loc_40E178
0x40e1a6  inc     ecx
0x40e1a7  cmp     ecx, 38Dh
0x40e1ad  jb      short loc_40E190
0x40e1af  mov     eax, [edx+4]
0x40e1b2  push    8000h; dwFreeType
0x40e1b7  push    0; dwSize
0x40e1b9  push    edx; lpAddress
0x40e1ba  mov     [esi], eax
0x40e1bc  call    ds:__imp__VirtualFree@12; VirtualFree(x,x,x)
0x40e1c2  mov     dword_40F470, 0
0x40e1cc  mov     edx, [esi]
0x40e1ce  test    edx, edx
0x40e1d0  jnz     short loc_40E170
0x40e1d2  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x40e1d8  mov     esi, lpBaseAddress
0x40e1de  mov     edi, eax
0x40e1e0  test    esi, esi
0x40e1e2  jz      short loc_40E20B
0x40e1e4  lea     eax, [esp+2E4h+var_2DC]
0x40e1e8  push    eax; lpflOldProtect
0x40e1e9  push    20h ; ' '; flNewProtect
0x40e1eb  push    10000h; dwSize
0x40e1f0  push    esi; lpAddress
  ... truncated ...
```
