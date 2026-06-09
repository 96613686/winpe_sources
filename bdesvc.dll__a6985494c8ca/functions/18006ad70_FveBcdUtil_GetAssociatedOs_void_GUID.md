# FveBcdUtil::GetAssociatedOs(void *,_GUID *)

- ea: `0x18006ad70`
- end: `0x18006af68`
- name: `?GetAssociatedOs@FveBcdUtil@@SAJPEAXPEAU_GUID@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(void *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18006af70`

## callees

- `0x180009f60`
- `0x18001b890`
- `0x180034070`
- `0x180034610`
- `0x180069cb8`
- `0x18006ad70`
- `0x18006b0b8`
- `0x18006b260`
- `0x18006bdb8`

## import_xrefs

- `bcd!BcdOpenObject` at `0x18006ae22`
- `bcd!BcdOpenObject` at `0x18006ae22`
- `bcd!BcdCloseObject` at `0x18006af23`
- `bcd!BcdCloseObject` at `0x18007d230`
- `bcd!BcdCloseObject` at `0x18006af23`
- `bcd!BcdCloseObject` at `0x18007d230`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::GetAssociatedOs(void *a1, struct _GUID *a2)
{
  unsigned __int8 v4; // r14
  int DoesRegKeyExist; // ebx
  int v6; // eax
  int BcdElementData; // eax
  unsigned int v8; // esi
  unsigned int i; // edi
  struct _GUID *v10; // r12
  int IsAssociatedOS; // eax
  unsigned __int8 v13[4]; // [rsp+20h] [rbp-68h] BYREF
  int v14; // [rsp+24h] [rbp-64h]
  int v15; // [rsp+28h] [rbp-60h] BYREF
  unsigned int v16; // [rsp+2Ch] [rbp-5Ch] BYREF
  void *v17; // [rsp+30h] [rbp-58h] BYREF
  void *Block; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v19; // [rsp+40h] [rbp-48h]
  struct _GUID v20; // [rsp+48h] [rbp-40h] BYREF

  v20 = 0;
  v17 = 0;
  Block = 0;
  v16 = 0;
  v4 = 0;
  v13[0] = 0;
  v15 = 0;
  DoesRegKeyExist = NgscbpDoesRegKeyExist(a1, a2, &v15);
  v14 = DoesRegKeyExist;
  if ( DoesRegKeyExist >= 0 )
  {
    if ( !v15 )
    {
LABEL_3:
      DoesRegKeyExist = -2147024809;
      v14 = -2147024809;
      goto LABEL_18;
    }
    DoesRegKeyExist = FveBcdUtil::GetCurrentOsGuid(a1, &v20);
    v14 = DoesRegKeyExist;
    if ( DoesRegKeyExist >= 0 )
    {
      v6 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v17);
      DoesRegKeyExist = FromNtStatus(v6);
      v14 = DoesRegKeyExist;
      if ( DoesRegKeyExist >= 0 )
      {
        BcdElementData = FveBcdUtil::GetBcdElementData(v17, 0x24000001u, &Block, &v16);
        DoesRegKeyExist = FromNtStatus(BcdElementData);
        v14 = DoesRegKeyExist;
        if ( DoesRegKeyExist >= 0 )
        {
          if ( (v16 & 0xF) != 0 )
            goto LABEL_3;
          v8 = v16 >> 4;
          for ( i = 0; ; ++i )
          {
            v19 = i;
            if ( i >= v8 )
              break;
            v10 = (struct _GUID *)((char *)Block + 16 * i);
            IsAssociatedOS = FveBcdUtil::IsAssociatedOS(a1, v10, &v20, v13);
            DoesRegKeyExist = FromNtStatus(IsAssociatedOS);
            v14 = DoesRegKeyExist;
            if ( DoesRegKeyExist < 0 )
              goto LABEL_18;
            v4 = v13[0];
            if ( v13[0] )
            {
              *a2 = *v10;
              break;
            }
          }
          if ( !v4 )
          {
            DoesRegKeyExist = -2147024894;
            v14 = -2147024894;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                73,
                &WPP_355f2e428fa63e5d859506595e3b2086_Traceguids,
                2147942402LL);
          }
        }
      }
    }
  }
LABEL_18:
  if ( v17 )
    BcdCloseObject(v17);
  if ( Block )
    operator delete(Block);
  return (unsigned int)DoesRegKeyExist;
}

```

## disassembly

```asm
0x18006ad70  mov     r11, rsp
0x18006ad73  mov     [r11+18h], rbx
0x18006ad77  mov     [r11+20h], rsi
0x18006ad7b  push    rdi
0x18006ad7c  push    r12
0x18006ad7e  push    r13
0x18006ad80  push    r14
0x18006ad82  push    r15
0x18006ad84  sub     rsp, 60h
0x18006ad88  mov     rax, cs:__security_cookie
0x18006ad8f  xor     rax, rsp
0x18006ad92  mov     [rsp+88h+var_30], rax
0x18006ad97  mov     r13, rdx
0x18006ad9a  mov     r15, rcx
0x18006ad9d  xorps   xmm0, xmm0
0x18006ada0  movups  xmmword ptr [rsp+88h+var_40.Data1], xmm0
0x18006ada5  mov     qword ptr [r11-58h], 0
0x18006adad  mov     qword ptr [r11-50h], 0
0x18006adb5  mov     [rsp+88h+var_5C], 0
0x18006adbd  xor     r14b, r14b
0x18006adc0  mov     [r11-68h], r14b
0x18006adc4  mov     [rsp+88h+var_60], 0
0x18006adcc  lea     r8, [r11-60h]
0x18006add0  call    NgscbpDoesRegKeyExist
0x18006add5  mov     ebx, eax
0x18006add7  mov     [rsp+88h+var_64], eax
0x18006addb  test    eax, eax
0x18006addd  js      loc_18006AF19
0x18006ade3  cmp     [rsp+88h+var_60], 0
0x18006ade8  jnz     short loc_18006ADF8
0x18006adea  mov     ebx, 80070057h
0x18006adef  mov     [rsp+88h+var_64], ebx
0x18006adf3  jmp     loc_18006AF19
0x18006adf8  lea     rdx, [rsp+88h+var_40]; struct _GUID *
0x18006adfd  mov     rcx, r15; void *
0x18006ae00  call    ?GetCurrentOsGuid@FveBcdUtil@@SAJPEAXPEAU_GUID@@@Z; FveBcdUtil::GetCurrentOsGuid(void *,_GUID *)
0x18006ae05  mov     ebx, eax
0x18006ae07  mov     [rsp+88h+var_64], eax
0x18006ae0b  test    eax, eax
0x18006ae0d  js      loc_18006AF19
0x18006ae13  lea     r8, [rsp+88h+var_58]
0x18006ae18  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18006ae1f  mov     rcx, r15
0x18006ae22  call    cs:__imp_BcdOpenObject
0x18006ae29  nop     dword ptr [rax+rax+00h]
0x18006ae2e  mov     ecx, eax; int
0x18006ae30  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18006ae35  mov     ebx, eax
0x18006ae37  mov     [rsp+88h+var_64], eax
0x18006ae3b  test    eax, eax
0x18006ae3d  js      loc_18006AF19
0x18006ae43  lea     r9, [rsp+88h+var_5C]; unsigned int *
0x18006ae48  lea     r8, [rsp+88h+Block]; void **
0x18006ae4d  mov     edx, 24000001h; unsigned int
0x18006ae52  mov     rcx, [rsp+88h+var_58]; void *
0x18006ae57  call    ?GetBcdElementData@FveBcdUtil@@SAJPEAXKPEAPEAXPEAK@Z; FveBcdUtil::GetBcdElementData(void *,ulong,void * *,ulong *)
0x18006ae5c  mov     ecx, eax; int
0x18006ae5e  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18006ae63  mov     ebx, eax
0x18006ae65  mov     [rsp+88h+var_64], eax
0x18006ae69  test    eax, eax
0x18006ae6b  js      loc_18006AF19
0x18006ae71  mov     esi, [rsp+88h+var_5C]
0x18006ae75  test    sil, 0Fh
0x18006ae79  jnz     loc_18006ADEA
0x18006ae7f  shr     esi, 4
0x18006ae82  xor     edi, edi
0x18006ae84  mov     [rsp+88h+var_48], edi
0x18006ae88  cmp     edi, esi
0x18006ae8a  jnb     short loc_18006AED9
0x18006ae8c  mov     r12d, edi
0x18006ae8f  shl     r12, 4
0x18006ae93  add     r12, [rsp+88h+Block]
0x18006ae98  lea     r9, [rsp+88h+var_68]; unsigned __int8 *
0x18006ae9d  lea     r8, [rsp+88h+var_40]; struct _GUID *
0x18006aea2  mov     rdx, r12; struct _GUID *
0x18006aea5  mov     rcx, r15; void *
0x18006aea8  call    ?IsAssociatedOS@FveBcdUtil@@SAJPEAXPEAU_GUID@@1PEAE@Z; FveBcdUtil::IsAssociatedOS(void *,_GUID *,_GUID *,uchar *)
0x18006aead  mov     ecx, eax; int
0x18006aeaf  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18006aeb4  mov     ebx, eax
0x18006aeb6  mov     [rsp+88h+var_64], eax
0x18006aeba  test    eax, eax
0x18006aebc  js      short loc_18006AF19
0x18006aebe  mov     r14b, [rsp+88h+var_68]
0x18006aec3  test    r14b, r14b
0x18006aec6  jz      short loc_18006AED5
0x18006aec8  movups  xmm0, xmmword ptr [r12]
0x18006aecd  movdqu  xmmword ptr [r13+0], xmm0
0x18006aed3  jmp     short loc_18006AED9
0x18006aed5  inc     edi
0x18006aed7  jmp     short loc_18006AE84
0x18006aed9  test    r14b, r14b
0x18006aedc  jnz     short loc_18006AF19
0x18006aede  mov     ebx, 80070002h
0x18006aee3  mov     [rsp+88h+var_64], ebx
0x18006aee7  lea     rax, WPP_GLOBAL_Control
0x18006aeee  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aef5  cmp     rcx, rax
0x18006aef8  jz      short loc_18006AF19
0x18006aefa  test    byte ptr [rcx+1Ch], 2
0x18006aefe  jz      short loc_18006AF19
0x18006af00  mov     edx, 49h ; 'I'
0x18006af05  mov     r9d, ebx
0x18006af08  lea     r8, WPP_355f2e428fa63e5d859506595e3b2086_Traceguids
0x18006af0f  mov     rcx, [rcx+10h]
0x18006af13  call    WPP_SF_d
0x18006af18  nop
0x18006af19  mov     rcx, [rsp+88h+var_58]
0x18006af1e  test    rcx, rcx
0x18006af21  jz      short loc_18006AF2F
0x18006af23  call    cs:__imp_BcdCloseObject
0x18006af2a  nop     dword ptr [rax+rax+00h]
0x18006af2f  mov     rcx, [rsp+88h+Block]; Block
0x18006af34  test    rcx, rcx
0x18006af37  jz      short loc_18006AF3E
0x18006af39  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006af3e  mov     eax, ebx
0x18006af40  mov     rcx, [rsp+88h+var_30]
0x18006af45  xor     rcx, rsp; StackCookie
0x18006af48  call    __security_check_cookie
0x18006af4d  lea     r11, [rsp+88h+var_28]
0x18006af52  mov     rbx, [r11+40h]
0x18006af56  mov     rsi, [r11+48h]
0x18006af5a  mov     rsp, r11
0x18006af5d  pop     r15
0x18006af5f  pop     r14
0x18006af61  pop     r13
0x18006af63  pop     r12
0x18006af65  pop     rdi
0x18006af66  retn
0x18007d21e  push    rbp
0x18007d220  sub     rsp, 20h
0x18007d224  mov     rbp, rdx
0x18007d227  mov     rcx, [rbp+30h]
0x18007d22b  test    rcx, rcx
0x18007d22e  jz      short loc_18007D23D
0x18007d230  call    cs:__imp_BcdCloseObject
0x18007d237  nop     dword ptr [rax+rax+00h]
0x18007d23c  nop
0x18007d23d  mov     rcx, [rbp+38h]; Block
0x18007d241  test    rcx, rcx
0x18007d244  jz      short loc_18007D24C
0x18007d246  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007d24b  nop
0x18007d24c  add     rsp, 20h
0x18007d250  pop     rbp
0x18007d251  retn
```
