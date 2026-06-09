# AiGetPlugins

- ea: `0x140029714`
- end: `0x1400299c5`
- name: `AiGetPlugins`
- size: `689`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x14002459c`
- `0x140024978`

## callees

- `0x1400016a8`
- `0x1400016d8`
- `0x1400032d4`
- `0x140006a20`
- `0x140025450`
- `0x140029714`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!ZwQueryInformationFile` at `0x140029764`
- `ntoskrnl!ZwQueryInformationFile` at `0x140029764`

## pseudocode

```c
__int64 __fastcall AiGetPlugins(HANDLE Handle, _QWORD *a2)
{
  _DWORD *v4; // rdi
  NTSTATUS File; // ebx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v7; // rdx
  _DWORD *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  unsigned int v11; // r10d
  unsigned int v12; // ecx
  __int64 v13; // rsi
  unsigned int v14; // ebp
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // r9d
  _DWORD *v18; // rdx
  unsigned int i; // r9d
  unsigned int v20; // ecx
  unsigned int v21; // r11d
  unsigned int v22; // ecx
  unsigned int v23; // r11d
  char *v24; // rdx
  unsigned int j; // r8d
  unsigned int v26; // ecx
  unsigned int v27; // r9d
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  struct _IO_STATUS_BLOCK v31; // [rsp+30h] [rbp-58h] BYREF
  __int128 v32; // [rsp+40h] [rbp-48h] BYREF
  __int64 v33; // [rsp+50h] [rbp-38h]

  v32 = 0;
  v33 = 0;
  v4 = 0;
  v31 = 0;
  File = ZwQueryInformationFile(Handle, &v31, &v32, 0x18u, FileStandardInformation);
  if ( File < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
    {
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v7 = 18;
LABEL_5:
      WPP_SF_D(AttachedDevice, v7, WPP_0961c2f37d1b3ad2f2ca69bd50809778_Traceguids, (unsigned int)File);
      goto LABEL_46;
    }
    goto LABEL_46;
  }
  if ( HIDWORD(v32) || DWORD2(v32) < 0x20 )
  {
LABEL_45:
    File = -1073741811;
    goto LABEL_46;
  }
  v8 = (_DWORD *)AiAlloc(DWORD2(v32));
  v4 = v8;
  if ( !v8 )
  {
    File = -1073741801;
    goto LABEL_46;
  }
  File = AiReadFile(Handle, v9, v8, DWORD2(v32));
  if ( File >= 0 )
  {
    if ( *v4 != 1179414593 )
      goto LABEL_41;
    if ( v4[1] != 1 )
      goto LABEL_41;
    v10 = (unsigned int)v4[2];
    v11 = v4[3];
    v12 = v10 + 36 * v11;
    if ( v12 < (unsigned int)v10 )
      goto LABEL_41;
    if ( v12 <= DWORD2(v32)
      && (v13 = (unsigned int)v4[4], v14 = v4[5], v15 = v13 + 28 * v14, v15 >= (unsigned int)v13)
      && v15 <= DWORD2(v32)
      && (v16 = v4[6], v17 = v16 + 16 * v4[7], v17 >= v16)
      && v17 <= DWORD2(v32) )
    {
      v18 = (_DWORD *)((char *)v4 + v10);
      for ( i = 0; i < v11; ++i )
      {
        v20 = v18[5];
        v21 = v20 + v18[6];
        if ( v21 < v20 || v21 > DWORD2(v32) || (v22 = v18[7], v23 = v22 + v18[8], v23 < v22) || v23 > v14 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21);
          }
          goto LABEL_45;
        }
        v18 += 9;
      }
      v24 = (char *)v4 + v13;
      for ( j = 0; ; ++j )
      {
        if ( j >= v14 )
        {
          *a2 = v4;
          v4 = 0;
          goto LABEL_46;
        }
        v26 = *((_DWORD *)v24 + 5);
        v27 = v26 + *((_DWORD *)v24 + 6);
        if ( v27 < v26 || v27 > v4[7] )
          break;
        v24 += 28;
      }
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
      {
        v29 = 22;
        goto LABEL_44;
      }
    }
    else
    {
LABEL_41:
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
      {
        v29 = 20;
LABEL_44:
        WPP_SF_(v28->AttachedDevice, v29, WPP_0961c2f37d1b3ad2f2ca69bd50809778_Traceguids);
      }
    }
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
  {
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v7 = 19;
    goto LABEL_5;
  }
LABEL_46:
  AiFree(v4);
  return (unsigned int)File;
}

```

## disassembly

```asm
0x140029714  mov     r11, rsp
0x140029717  mov     [r11+18h], rbx
0x14002971b  push    rbp
0x14002971c  push    rsi
0x14002971d  push    rdi
0x14002971e  push    r14
0x140029720  push    r15
0x140029722  sub     rsp, 60h
0x140029726  mov     rax, cs:__security_cookie
0x14002972d  xor     rax, rsp
0x140029730  mov     [rsp+88h+var_30], rax
0x140029735  xor     eax, eax
0x140029737  mov     [rsp+88h+FileInformationClass], 5; FileInformationClass
0x14002973f  xorps   xmm0, xmm0
0x140029742  lea     r8, [r11-48h]; FileInformation
0x140029746  mov     r15, rdx
0x140029749  mov     rsi, rcx
0x14002974c  movups  [rsp+88h+var_48], xmm0
0x140029751  lea     r9d, [rax+18h]; Length
0x140029755  mov     [r11-38h], rax
0x140029759  lea     rdx, [r11-58h]; IoStatusBlock
0x14002975d  xor     edi, edi
0x14002975f  movups  [rsp+88h+var_58], xmm0
0x140029764  call    cs:__imp_ZwQueryInformationFile
0x14002976b  nop     dword ptr [rax+rax+00h]
0x140029770  mov     ebx, eax
0x140029772  test    eax, eax
0x140029774  jns     short loc_1400297B4
0x140029776  mov     r10, cs:WPP_GLOBAL_Control
0x14002977d  lea     rax, WPP_GLOBAL_Control
0x140029784  cmp     r10, rax
0x140029787  jz      loc_140029999
0x14002978d  mov     ecx, [r10+2Ch]
0x140029791  test    cl, cl
0x140029793  jns     loc_140029999
0x140029799  mov     rcx, [r10+18h]
0x14002979d  lea     edx, [rdi+12h]
0x1400297a0  lea     r8, WPP_0961c2f37d1b3ad2f2ca69bd50809778_Traceguids
0x1400297a7  mov     r9d, ebx
0x1400297aa  call    WPP_SF_D
0x1400297af  jmp     loc_140029999
0x1400297b4  cmp     dword ptr [rsp+88h+var_48+0Ch], edi
0x1400297b8  jnz     loc_140029994
0x1400297be  cmp     dword ptr [rsp+88h+var_48+8], 20h ; ' '
0x1400297c3  jb      loc_140029994
0x1400297c9  mov     ecx, dword ptr [rsp+88h+var_48+8]
0x1400297cd  call    AiAlloc
0x1400297d2  mov     rdi, rax
0x1400297d5  test    rax, rax
0x1400297d8  jnz     short loc_1400297E4
0x1400297da  mov     ebx, 0C0000017h
0x1400297df  jmp     loc_140029999
0x1400297e4  mov     r9d, dword ptr [rsp+88h+var_48+8]
0x1400297e9  mov     r8, rdi
0x1400297ec  mov     rcx, rsi; Handle
0x1400297ef  call    AiReadFile
0x1400297f4  mov     ebx, eax
0x1400297f6  test    eax, eax
0x1400297f8  jns     short loc_14002982A
0x1400297fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140029801  lea     rax, WPP_GLOBAL_Control
0x140029808  cmp     rcx, rax
0x14002980b  jz      loc_140029999
0x140029811  mov     eax, [rcx+2Ch]
0x140029814  test    al, al
0x140029816  jns     loc_140029999
0x14002981c  mov     rcx, [rcx+18h]
0x140029820  mov     edx, 13h
0x140029825  jmp     loc_1400297A0
0x14002982a  cmp     dword ptr [rdi], 464C7041h
0x140029830  jnz     loc_140029965
0x140029836  cmp     dword ptr [rdi+4], 1
0x14002983a  jnz     loc_140029965
0x140029840  mov     edx, [rdi+8]
0x140029843  mov     r10d, [rdi+0Ch]
0x140029847  lea     eax, [r10+r10*8]
0x14002984b  lea     ecx, [rdx+rax*4]
0x14002984e  cmp     ecx, edx
0x140029850  jb      loc_140029965
0x140029856  mov     r8d, dword ptr [rsp+88h+var_48+8]
0x14002985b  cmp     ecx, r8d
0x14002985e  ja      loc_140029965
0x140029864  mov     esi, [rdi+10h]
0x140029867  mov     ebp, [rdi+14h]
0x14002986a  imul    ecx, ebp, 1Ch
0x14002986d  add     ecx, esi
0x14002986f  cmp     ecx, esi
0x140029871  jb      loc_140029965
0x140029877  cmp     ecx, r8d
0x14002987a  ja      loc_140029965
0x140029880  mov     ecx, [rdi+18h]
0x140029883  mov     r14d, [rdi+1Ch]
0x140029887  mov     r9d, r14d
0x14002988a  shl     r9d, 4
0x14002988e  add     r9d, ecx
0x140029891  cmp     r9d, ecx
0x140029894  jb      loc_140029965
0x14002989a  cmp     r9d, r8d
0x14002989d  ja      loc_140029965
0x1400298a3  add     rdx, rdi
0x1400298a6  xor     r9d, r9d
0x1400298a9  cmp     r9d, r10d
0x1400298ac  jnb     short loc_140029914
0x1400298ae  mov     ecx, [rdx+14h]
0x1400298b1  mov     r11d, [rdx+18h]
0x1400298b5  add     r11d, ecx
0x1400298b8  cmp     r11d, ecx
0x1400298bb  jb      short loc_1400298DF
0x1400298bd  cmp     r11d, r8d
0x1400298c0  ja      short loc_1400298DF
0x1400298c2  mov     ecx, [rdx+1Ch]
0x1400298c5  mov     r11d, [rdx+20h]
0x1400298c9  add     r11d, ecx
0x1400298cc  cmp     r11d, ecx
0x1400298cf  jb      short loc_1400298DF
0x1400298d1  cmp     r11d, ebp
0x1400298d4  ja      short loc_1400298DF
0x1400298d6  inc     r9d
0x1400298d9  add     rdx, 24h ; '$'
0x1400298dd  jmp     short loc_1400298A9
0x1400298df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400298e6  lea     rax, WPP_GLOBAL_Control
0x1400298ed  cmp     rcx, rax
0x1400298f0  jz      loc_140029994
0x1400298f6  mov     eax, [rcx+2Ch]
0x1400298f9  test    al, al
0x1400298fb  jns     loc_140029994
0x140029901  mov     rcx, [rcx+18h]
0x140029905  mov     edx, 15h
0x14002990a  call    WPP_SF_d
0x14002990f  jmp     loc_140029994
0x140029914  lea     rdx, [rdi+rsi]
0x140029918  xor     r8d, r8d
0x14002991b  cmp     r8d, ebp
0x14002991e  jnb     short loc_14002995E
0x140029920  mov     ecx, [rdx+14h]
0x140029923  mov     r9d, [rdx+18h]
0x140029927  add     r9d, ecx
0x14002992a  cmp     r9d, ecx
0x14002992d  jb      short loc_14002993D
0x14002992f  cmp     r9d, r14d
0x140029932  ja      short loc_14002993D
0x140029934  inc     r8d
0x140029937  add     rdx, 1Ch
0x14002993b  jmp     short loc_14002991B
0x14002993d  mov     rcx, cs:WPP_GLOBAL_Control
0x140029944  lea     rax, WPP_GLOBAL_Control
0x14002994b  cmp     rcx, rax
0x14002994e  jz      short loc_140029994
0x140029950  mov     eax, [rcx+2Ch]
0x140029953  test    al, al
0x140029955  jns     short loc_140029994
0x140029957  mov     edx, 16h
0x14002995c  jmp     short loc_140029984
0x14002995e  mov     [r15], rdi
0x140029961  xor     edi, edi
0x140029963  jmp     short loc_140029999
0x140029965  mov     rcx, cs:WPP_GLOBAL_Control
0x14002996c  lea     rax, WPP_GLOBAL_Control
0x140029973  cmp     rcx, rax
0x140029976  jz      short loc_140029994
0x140029978  mov     eax, [rcx+2Ch]
0x14002997b  test    al, al
0x14002997d  jns     short loc_140029994
0x14002997f  mov     edx, 14h
0x140029984  mov     rcx, [rcx+18h]
0x140029988  lea     r8, WPP_0961c2f37d1b3ad2f2ca69bd50809778_Traceguids
0x14002998f  call    WPP_SF_
0x140029994  mov     ebx, 0C000000Dh
0x140029999  mov     rcx, rdi
0x14002999c  call    AiFree
0x1400299a1  mov     eax, ebx
0x1400299a3  mov     rcx, [rsp+88h+var_30]
0x1400299a8  xor     rcx, rsp; StackCookie
0x1400299ab  call    __security_check_cookie
0x1400299b0  mov     rbx, [rsp+88h+arg_10]
0x1400299b8  add     rsp, 60h
0x1400299bc  pop     r15
0x1400299be  pop     r14
0x1400299c0  pop     rdi
0x1400299c1  pop     rsi
0x1400299c2  pop     rbp
0x1400299c3  retn
```
