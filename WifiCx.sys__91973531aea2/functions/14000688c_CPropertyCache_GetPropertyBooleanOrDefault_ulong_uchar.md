# CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)

- ea: `0x14000688c`
- end: `0x1400069d3`
- name: `?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z`
- size: `327`
- prototype: `unsigned __int8 __fastcall(CPropertyCache *__hidden this, unsigned int, unsigned __int8)`
- caller_count: `37`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140027b68`
- `0x14005758c`
- `0x140057ef0`
- `0x140061fc0`
- `0x140062ef0`
- `0x14006abe0`
- `0x14006b040`
- `0x140072330`
- `0x140076c10`
- `0x140077e40`
- `0x140078d60`
- `0x14007f6a8`
- `0x140084068`
- `0x140088270`
- `0x140088afc`
- `0x140089578`
- `0x1400896ac`
- `0x1400898c0`
- `0x14008a338`
- `0x14008ba40`
- `0x140090850`
- `0x1400a19c0`
- `0x1400a22d4`
- `0x1400a2b64`
- `0x1400a3584`
- `0x1400a5fec`
- `0x1400a621c`
- `0x1400a6c04`
- `0x1400abc80`
- `0x1400acd00`
- `0x1400adae0`
- `0x1400b0128`
- `0x1400b0448`
- `0x1400b1d28`
- `0x1400b3678`
- `0x1400b37f8`
- `0x1400b511c`

## callees

- `0x14000688c`
- `0x1400069dc`
- `0x14000c778`

## pseudocode

```c
char __fastcall CPropertyCache::GetPropertyBooleanOrDefault(CPropertyCache *this, unsigned int a2, char a3)
{
  char v3; // si
  __int64 v5; // rdi
  __int64 v6; // rcx
  int v7; // ebx
  __int64 v9; // [rsp+28h] [rbp-50h]
  int v10; // [rsp+28h] [rbp-50h]
  int v11; // [rsp+28h] [rbp-50h]

  v3 = a2;
  v5 = 0;
  if ( a2 >= *((_DWORD *)this + 2) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return a3;
    v11 = a2;
    LOBYTE(a2) = 2;
    v7 = -1073741811;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      19,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      v11);
  }
  else
  {
    v6 = 56LL * a2 + *((_QWORD *)this + 2);
    if ( *(_BYTE *)(v6 + 8) )
    {
      v5 = v6;
    }
    else
    {
      if ( !*(_QWORD *)(v6 + 48) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v10 = a2;
          LOBYTE(a2) = 4;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            1,
            20,
            (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
            v10);
        }
        v7 = -1073741436;
        goto LABEL_12;
      }
      v5 = *(_QWORD *)(v6 + 48);
    }
    v7 = 0;
  }
LABEL_12:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 5;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LODWORD(v9) = v7;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        22,
        (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
        v9);
    }
  }
  if ( !v7 )
    return *(_BYTE *)(v5 + 16);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_DD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      16,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      v3,
      v7);
  }
  return a3;
}

```

## disassembly

```asm
0x14000688c  push    rbx
0x14000688e  push    rbp
0x14000688f  push    rsi
0x140006890  push    rdi
0x140006891  push    r13
0x140006893  push    r14
0x140006895  push    r15
0x140006897  sub     rsp, 40h
0x14000689b  xor     r14d, r14d
0x14000689e  mov     esi, edx
0x1400068a0  lea     r15, WPP_RECORDER_INITIALIZED
0x1400068a7  mov     bpl, r8b
0x1400068aa  lea     r13, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x1400068b1  mov     edi, r14d
0x1400068b4  cmp     edx, [rcx+8]
0x1400068b7  jnb     short loc_140006913
0x1400068b9  mov     rcx, [rcx+10h]
0x1400068bd  imul    r8, rsi, 38h ; '8'
0x1400068c1  add     rcx, r8
0x1400068c4  cmp     [rcx+8], r14b
0x1400068c8  jnz     short loc_14000690B
0x1400068ca  mov     rax, [rcx+30h]
0x1400068ce  test    rax, rax
0x1400068d1  jnz     short loc_140006906
0x1400068d3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400068da  jz      short loc_1400068FF
0x1400068dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068e3  lea     r9d, [r14+14h]
0x1400068e7  mov     dword ptr [rsp+78h+var_50], esi
0x1400068eb  lea     r8d, [r14+1]
0x1400068ef  mov     dl, 4
0x1400068f1  mov     [rsp+78h+var_58], r13
0x1400068f6  mov     rcx, [rcx+40h]
0x1400068fa  call    WPP_RECORDER_SF_d
0x1400068ff  mov     ebx, 0C0000184h
0x140006904  jmp     short loc_14000694A
0x140006906  mov     rdi, rax
0x140006909  jmp     short loc_14000690E
0x14000690b  mov     rdi, rcx
0x14000690e  mov     ebx, r14d
0x140006911  jmp     short loc_14000694A
0x140006913  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000691a  jz      loc_1400069C0
0x140006920  mov     rcx, cs:WPP_GLOBAL_Control
0x140006927  mov     r9d, 13h
0x14000692d  mov     dword ptr [rsp+78h+var_50], esi
0x140006931  mov     dl, 2
0x140006933  mov     ebx, 0C000000Dh
0x140006938  mov     [rsp+78h+var_58], r13
0x14000693d  mov     rcx, [rcx+40h]
0x140006941  lea     r8d, [r9-12h]
0x140006945  call    WPP_RECORDER_SF_d
0x14000694a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006951  jz      short loc_140006984
0x140006953  mov     rcx, cs:WPP_GLOBAL_Control
0x14000695a  mov     dl, 5
0x14000695c  cmp     [rcx+29h], dl
0x14000695f  jnb     short loc_140006968
0x140006961  cmp     [rcx+48h], r14w
0x140006966  jz      short loc_140006984
0x140006968  mov     rcx, [rcx+40h]
0x14000696c  mov     r9d, 16h
0x140006972  mov     dword ptr [rsp+78h+var_50], ebx
0x140006976  mov     [rsp+78h+var_58], r13
0x14000697b  lea     r8d, [r9-15h]
0x14000697f  call    WPP_RECORDER_SF_d
0x140006984  test    ebx, ebx
0x140006986  jnz     short loc_14000698E
0x140006988  mov     bpl, [rdi+10h]
0x14000698c  jmp     short loc_1400069C0
0x14000698e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140006995  jz      short loc_1400069C0
0x140006997  mov     rcx, cs:WPP_GLOBAL_Control
0x14000699e  mov     r9d, 10h
0x1400069a4  mov     [rsp+78h+var_48], ebx
0x1400069a8  mov     dl, 4
0x1400069aa  mov     dword ptr [rsp+78h+var_50], esi
0x1400069ae  mov     [rsp+78h+var_58], r13
0x1400069b3  mov     rcx, [rcx+40h]
0x1400069b7  lea     r8d, [r9-0Fh]
0x1400069bb  call    WPP_RECORDER_SF_DD
0x1400069c0  mov     al, bpl
0x1400069c3  add     rsp, 40h
0x1400069c7  pop     r15
0x1400069c9  pop     r14
0x1400069cb  pop     r13
0x1400069cd  pop     rdi
0x1400069ce  pop     rsi
0x1400069cf  pop     rbp
0x1400069d0  pop     rbx
0x1400069d1  retn
```
