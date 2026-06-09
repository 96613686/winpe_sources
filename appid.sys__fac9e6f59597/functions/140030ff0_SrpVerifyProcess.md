# SrpVerifyProcess

- ea: `0x140030ff0`
- end: `0x140031360`
- name: `SrpVerifyProcess`
- size: `880`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int@<r8d>, int, char, int, __int64, __int64, char, PFILE_OBJECT, HANDLE)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x1400373b0`

## callees

- `0x140001450`
- `0x140022afc`
- `0x1400237dc`
- `0x140023934`
- `0x14002f560`
- `0x140030fa0`
- `0x140030ff0`
- `0x140031370`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14003130a`
- `ntoskrnl!EtwWrite` at `0x14003130a`

## string_xrefs

- `0x14003105a`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`
- `0x1400310ab`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

## pseudocode

```c
__int64 __fastcall SrpVerifyProcess(
        void *a1,
        void *a2,
        __int64 a3,
        char a4,
        UNICODE_STRING *a5,
        char a6,
        int a7,
        const UNICODE_STRING *a8,
        __int64 a9,
        unsigned __int8 a10,
        PFILE_OBJECT FileObject,
        HANDLE FileHandle)
{
  int v12; // esi
  unsigned int v13; // r14d
  bool v17; // r15
  bool v18; // di
  bool v19; // di
  int v20; // eax
  char v21; // dl
  char v22; // r9
  int v23; // eax
  __int128 *v24; // rdi
  __int64 v26; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING v27; // [rsp+78h] [rbp-21h] BYREF
  struct _UNICODE_STRING v28[4]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v29; // [rsp+F0h] [rbp+57h] BYREF
  char v30; // [rsp+F8h] [rbp+5Fh] BYREF

  v12 = 0;
  v13 = 0;
  LODWORD(v29) = 0;
  v17 = !a4 && *(int *)(a3 + 32) >= 0 && *(_DWORD *)(*(_QWORD *)(a3 + 40) + 12LL);
  v18 = *(int *)(a3 + 176) >= 0 && *(_DWORD *)(*(_QWORD *)(a3 + 184) + 12LL);
  *(_QWORD *)&v28[0].Length = 10879140;
  v28[0].Buffer = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\SMARTLOCKER";
  *(_QWORD *)&v27.Length = 1048590;
  v27.Buffer = L"ENABLED";
  v26 = 0;
  v30 = (int)AiRegReadQwordValue(0, v28, &v27, &v26) >= 0 && v26;
  *(_QWORD *)&v27.Length = 10879140;
  v27.Buffer = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\SMARTLOCKER";
  *(_QWORD *)&v28[0].Length = 1179664;
  v28[0].Buffer = L"DISABLED";
  v26 = 0;
  v19 = ((int)AiRegReadQwordValue(0, &v27, v28, &v26) < 0 || !v26) && (v18 || v30);
  if ( !a7 )
  {
    if ( dword_1400196E4 )
    {
      if ( v17 && !(unsigned __int8)SrpServiceBypass(a3, a10, 0, 0) )
      {
        v20 = SrppAccessCheck(a1, a3, a5, a6, 0, &v29);
        v12 = v29;
        v13 = v20;
        if ( v20 < 0 )
        {
          if ( (*(_DWORD *)(*(_QWORD *)(a3 + 40) + 24LL) & 0x20) == 0
            || (v29 & 0x20000) != 0
            || !SrpIsWindowsSigned((__int64)FileObject, (__int64)FileHandle) )
          {
            goto LABEL_31;
          }
          v13 = 0;
          v12 = 0x10000;
        }
      }
    }
    if ( *(_BYTE *)(a3 + 260) )
      v13 = SrpInvokePlugins(a3, 0, (__int128 *)a9);
LABEL_31:
    if ( !dword_1400196E4 )
      return v13;
    if ( !v19 )
      return v13;
    if ( (unsigned __int8)SrpServiceBypass(a3, a10, 0, 0) )
      return v13;
    v23 = SmartlockerVerifyProcess(
            a1,
            a2,
            a3,
            a5,
            a6,
            *(_DWORD *)(*(_QWORD *)(a9 + 56) + 16LL),
            *(_QWORD *)(a9 + 32),
            v12,
            FileObject,
            FileHandle,
            v21,
            v22,
            v30);
    if ( v23 < 0 || !*(_BYTE *)(a3 + 333) || (v12 & 0x20000) != 0 )
      return v13;
    return (unsigned int)v23;
  }
  if ( !dword_1400196E4 )
    goto LABEL_49;
  if ( *(int *)(a3 + 128) < 0 || !*(_DWORD *)(*(_QWORD *)(a3 + 136) + 12LL) )
  {
    if ( v17 && (*(_BYTE *)(*(_QWORD *)(a3 + 40) + 24LL) & 1) != 0 )
    {
      EtwWrite(qword_1400196F8, &SrpNoAppxRuleConfigured, 0, 0, 0);
      return (unsigned int)-1073740956;
    }
    goto LABEL_49;
  }
  v13 = SrppAccessCheck(a1, a3 + 96, a8, a6, a7, &v29);
  if ( (v13 & 0x80000000) == 0 )
  {
LABEL_49:
    v24 = (__int128 *)a9;
    goto LABEL_50;
  }
  if ( (v29 & 0x20000) == 0 )
  {
    v24 = (__int128 *)a9;
    v30 = 0;
    if ( (int)AiIsAppxInbox(*(_QWORD *)(a9 + 64), (bool *)&v30) >= 0 )
    {
      if ( v30 )
      {
        v13 = 0;
LABEL_50:
        if ( !*(_BYTE *)(a3 + 308) )
          return v13;
        return (unsigned int)SrpInvokePlugins(a3, 2, v24);
      }
    }
  }
  return v13;
}

```

## disassembly

```asm
0x140030ff0  push    rbp
0x140030ff2  push    rbx
0x140030ff3  push    rsi
0x140030ff4  push    r12
0x140030ff6  push    r13
0x140030ff8  push    r14
0x140030ffa  push    r15
0x140030ffc  lea     rbp, [rsp-7]
0x140031001  sub     rsp, 0A0h
0x140031008  xor     esi, esi
0x14003100a  xor     r14d, r14d
0x14003100d  mov     dword ptr [rbp+37h+arg_10], esi
0x140031010  mov     rbx, r8
0x140031013  mov     r13, rdx
0x140031016  mov     r12, rcx
0x140031019  test    r9b, r9b
0x14003101c  jnz     short loc_140031032
0x14003101e  cmp     [r8+20h], esi
0x140031022  jl      short loc_140031032
0x140031024  mov     rax, [r8+28h]
0x140031028  cmp     [rax+0Ch], esi
0x14003102b  jz      short loc_140031032
0x14003102d  mov     r15b, 1
0x140031030  jmp     short loc_140031035
0x140031032  xor     r15b, r15b
0x140031035  mov     [rsp+0D0h+arg_0], rdi
0x14003103d  cmp     [r8+0B0h], esi
0x140031044  jl      short loc_140031057
0x140031046  mov     rax, [r8+0B8h]
0x14003104d  cmp     [rax+0Ch], esi
0x140031050  jz      short loc_140031057
0x140031052  mov     dil, 1
0x140031055  jmp     short loc_14003105A
0x140031057  xor     dil, dil
0x14003105a  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x140031061  mov     [rbp+37h+var_48], 0A600A4h
0x140031069  mov     [rbp+37h+var_40], rax
0x14003106d  lea     r9, [rbp+37h+var_60]
0x140031071  lea     rax, aEnabled; "ENABLED"
0x140031078  mov     [rbp+37h+var_58], 10000Eh
0x140031080  lea     r8, [rbp+37h+var_58]
0x140031084  mov     [rbp+37h+var_50], rax
0x140031088  lea     rdx, [rbp+37h+var_48]
0x14003108c  mov     [rbp+37h+var_60], rsi
0x140031090  xor     ecx, ecx
0x140031092  call    AiRegReadQwordValue
0x140031097  test    eax, eax
0x140031099  js      short loc_1400310A7
0x14003109b  cmp     [rbp+37h+var_60], rsi
0x14003109f  jz      short loc_1400310A7
0x1400310a1  mov     [rbp+37h+arg_18], 1
0x1400310a5  jmp     short loc_1400310AB
0x1400310a7  mov     [rbp+37h+arg_18], sil
0x1400310ab  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x1400310b2  mov     [rbp+37h+var_58], 0A600A4h
0x1400310ba  mov     [rbp+37h+var_50], rax
0x1400310be  lea     r9, [rbp+37h+var_60]
0x1400310c2  lea     rax, aDisabled; "DISABLED"
0x1400310c9  mov     [rbp+37h+var_48], 120010h
0x1400310d1  lea     r8, [rbp+37h+var_48]
0x1400310d5  mov     [rbp+37h+var_40], rax
0x1400310d9  lea     rdx, [rbp+37h+var_58]
0x1400310dd  mov     [rbp+37h+var_60], rsi
0x1400310e1  xor     ecx, ecx
0x1400310e3  call    AiRegReadQwordValue
0x1400310e8  test    eax, eax
0x1400310ea  js      short loc_1400310F2
0x1400310ec  cmp     [rbp+37h+var_60], rsi
0x1400310f0  jnz     short loc_1400310FD
0x1400310f2  test    dil, dil
0x1400310f5  jnz     short loc_140031102
0x1400310f7  cmp     [rbp+37h+arg_18], sil
0x1400310fb  jnz     short loc_140031102
0x1400310fd  xor     dil, dil
0x140031100  jmp     short loc_140031105
0x140031102  mov     dil, 1
0x140031105  mov     eax, [rbp+37h+arg_30]
0x140031108  test    eax, eax
0x14003110a  jnz     loc_14003126C
0x140031110  cmp     cs:dword_1400196E4, esi
0x140031116  jz      short loc_140031195
0x140031118  test    r15b, r15b
0x14003111b  jz      short loc_140031195
0x14003111d  movzx   edx, [rbp+37h+arg_48]
0x140031124  xor     r9d, r9d
0x140031127  xor     r8d, r8d
0x14003112a  mov     rcx, rbx
0x14003112d  call    SrpServiceBypass
0x140031132  test    al, al
0x140031134  jnz     short loc_140031195
0x140031136  mov     r9d, dword ptr [rbp+37h+arg_28]
0x14003113a  lea     rax, [rbp+37h+arg_10]
0x14003113e  mov     r8, [rbp+37h+arg_20]
0x140031142  mov     rdx, rbx
0x140031145  mov     [rsp+0D0h+var_A8], rax; __int64
0x14003114a  mov     rcx, r12; HANDLE
0x14003114d  mov     byte ptr [rsp+0D0h+UserData], sil; char
0x140031152  call    SrppAccessCheck
0x140031157  mov     esi, dword ptr [rbp+37h+arg_10]
0x14003115a  mov     r14d, eax
0x14003115d  test    eax, eax
0x14003115f  jns     short loc_140031195
0x140031161  mov     rcx, [rbx+28h]
0x140031165  mov     edx, [rcx+18h]
0x140031168  shr     edx, 5
0x14003116b  test    dl, 1
0x14003116e  jz      short loc_1400311B2
0x140031170  bt      esi, 11h
0x140031174  jb      short loc_1400311B2
0x140031176  mov     rdx, [rbp+37h+arg_58]
0x14003117d  mov     rcx, [rbp+37h+arg_50]
0x140031184  call    SrpIsWindowsSigned
0x140031189  test    al, al
0x14003118b  jz      short loc_1400311B2
0x14003118d  xor     r14d, r14d
0x140031190  mov     esi, 10000h
0x140031195  cmp     byte ptr [rbx+104h], 0
0x14003119c  jz      short loc_1400311B2
0x14003119e  mov     r8, [rbp+37h+arg_40]
0x1400311a5  xor     edx, edx
0x1400311a7  mov     rcx, rbx
0x1400311aa  call    SrpInvokePlugins
0x1400311af  mov     r14d, eax
0x1400311b2  cmp     cs:dword_1400196E4, 0
0x1400311b9  jz      loc_140031341
0x1400311bf  test    dil, dil
0x1400311c2  jz      loc_140031341
0x1400311c8  movzx   edx, [rbp+37h+arg_48]
0x1400311cf  xor     r9d, r9d
0x1400311d2  xor     r8d, r8d
0x1400311d5  mov     rcx, rbx
0x1400311d8  call    SrpServiceBypass
0x1400311dd  test    al, al
0x1400311df  jnz     loc_140031341
0x1400311e5  movzx   r8d, [rbp+37h+arg_18]
0x1400311ea  mov     rax, [rbp+37h+arg_40]
0x1400311f1  mov     [rsp+0D0h+var_70], r8b; char
0x1400311f6  mov     r8, rbx; int
0x1400311f9  mov     [rsp+0D0h+var_78], r9b; char
0x1400311fe  mov     r9, [rbp+37h+arg_20]; int
0x140031202  mov     rcx, [rax+38h]
0x140031206  mov     rax, [rax+20h]
0x14003120a  mov     [rsp+0D0h+var_80], dl; char
0x14003120e  mov     rdx, [rbp+37h+arg_58]
0x140031215  mov     [rsp+0D0h+FileHandle], rdx; FileHandle
0x14003121a  mov     rdx, [rbp+37h+arg_50]
0x140031221  mov     [rsp+0D0h+FileObject], rdx; FileObject
0x140031226  mov     rdx, r13; int
0x140031229  mov     [rsp+0D0h+var_98], esi; int
0x14003122d  mov     [rsp+0D0h+var_A0], rax; __int64
0x140031232  mov     eax, [rcx+10h]
0x140031235  mov     rcx, r12; int
0x140031238  mov     dword ptr [rsp+0D0h+var_A8], eax; int
0x14003123c  mov     eax, dword ptr [rbp+37h+arg_28]
0x14003123f  mov     dword ptr [rsp+0D0h+UserData], eax; char
0x140031243  call    SmartlockerVerifyProcess
0x140031248  test    eax, eax
0x14003124a  js      loc_140031341
0x140031250  cmp     byte ptr [rbx+14Dh], 0
0x140031257  jz      loc_140031341
0x14003125d  bt      esi, 11h
0x140031261  jnb     loc_14003133E
0x140031267  jmp     loc_140031341
0x14003126c  cmp     cs:dword_1400196E4, esi
0x140031272  jz      loc_14003131E
0x140031278  lea     rdx, [rbx+60h]
0x14003127c  cmp     [rdx+20h], esi
0x14003127f  jl      short loc_1400312E2
0x140031281  mov     rcx, [rdx+28h]
0x140031285  cmp     [rcx+0Ch], esi
0x140031288  jz      short loc_1400312E2
0x14003128a  mov     r9d, dword ptr [rbp+37h+arg_28]
0x14003128e  lea     rcx, [rbp+37h+arg_10]
0x140031292  mov     r8, [rbp+37h+arg_38]
0x140031296  mov     [rsp+0D0h+var_A8], rcx; __int64
0x14003129b  mov     rcx, r12; HANDLE
0x14003129e  mov     byte ptr [rsp+0D0h+UserData], al; char
0x1400312a2  call    SrppAccessCheck
0x1400312a7  mov     r14d, eax
0x1400312aa  test    eax, eax
0x1400312ac  jns     short loc_14003131E
0x1400312ae  test    dword ptr [rbp+37h+arg_10], 20000h
0x1400312b5  jnz     loc_140031341
0x1400312bb  mov     rdi, [rbp+37h+arg_40]
0x1400312c2  lea     rdx, [rbp+37h+arg_18]
0x1400312c6  mov     [rbp+37h+arg_18], sil
0x1400312ca  mov     rcx, [rdi+40h]
0x1400312ce  call    AiIsAppxInbox
0x1400312d3  test    eax, eax
0x1400312d5  js      short loc_140031341
0x1400312d7  cmp     [rbp+37h+arg_18], sil
0x1400312db  jz      short loc_140031341
0x1400312dd  xor     r14d, r14d
0x1400312e0  jmp     short loc_140031325
0x1400312e2  test    r15b, r15b
0x1400312e5  jz      short loc_14003131E
0x1400312e7  mov     rax, [rbx+28h]
0x1400312eb  test    byte ptr [rax+18h], 1
0x1400312ef  jz      short loc_14003131E
0x1400312f1  mov     rcx, cs:qword_1400196F8; RegHandle
0x1400312f8  lea     rdx, SrpNoAppxRuleConfigured; EventDescriptor
0x1400312ff  xor     r9d, r9d; UserDataCount
0x140031302  mov     [rsp+0D0h+UserData], rsi; UserData
0x140031307  xor     r8d, r8d; ActivityId
0x14003130a  call    cs:__imp_EtwWrite
0x140031311  nop     dword ptr [rax+rax+00h]
0x140031316  mov     r14d, 0C0000364h
0x14003131c  jmp     short loc_140031341
0x14003131e  mov     rdi, [rbp+37h+arg_40]
0x140031325  cmp     [rbx+134h], sil
0x14003132c  jz      short loc_140031341
0x14003132e  mov     r8, rdi
0x140031331  mov     edx, 2
0x140031336  mov     rcx, rbx
0x140031339  call    SrpInvokePlugins
0x14003133e  mov     r14d, eax
0x140031341  mov     rdi, [rsp+0D0h+arg_0]
0x140031349  mov     eax, r14d
0x14003134c  add     rsp, 0A0h
0x140031353  pop     r15
0x140031355  pop     r14
0x140031357  pop     r13
0x140031359  pop     r12
0x14003135b  pop     rsi
0x14003135c  pop     rbx
0x14003135d  pop     rbp
0x14003135e  retn
```
