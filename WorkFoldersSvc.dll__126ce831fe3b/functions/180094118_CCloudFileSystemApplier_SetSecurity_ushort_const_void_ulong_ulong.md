# CCloudFileSystemApplier::SetSecurity(ushort const *,void *,ulong,ulong)

- ea: `0x180094118`
- end: `0x1800942a7`
- name: `?SetSecurity@CCloudFileSystemApplier@@AEAAJPEBGPEAXKK@Z`
- size: `399`
- prototype: `int(CCloudFileSystemApplier *__hidden this, const unsigned __int16 *, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800950b4`

## callees

- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x180094118`
- `0x180098eec`

## import_xrefs

- `ntdll!NtSetSecurityObject` at `0x180094254`
- `ntdll!NtSetSecurityObject` at `0x180094254`
- `ntdll!NtClose` at `0x180094281`
- `ntdll!NtClose` at `0x180094281`

## string_xrefs

- `0x180094199`: `CCloudFileSystemApplier::SetSecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCloudFileSystemApplier::SetSecurity(
        CCloudFileSystemApplier *this,
        const unsigned __int16 *a2,
        void *a3)
{
  _DWORD *v5; // rax
  char v6; // cl
  __int16 v7; // ax
  int v8; // ebx
  __int16 v9; // ax
  unsigned int v10; // eax
  int v12; // [rsp+40h] [rbp-20h] BYREF
  int v13; // [rsp+44h] [rbp-1Ch]
  char v14; // [rsp+48h] [rbp-18h]
  const char *v15; // [rsp+50h] [rbp-10h]
  __int64 v16; // [rsp+58h] [rbp-8h]
  HANDLE Handle; // [rsp+70h] [rbp+10h] BYREF

  Handle = this;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) == 0 )
    {
LABEL_8:
      v6 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 115, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( (v5[17] & 0x100) == 0 || *((_BYTE *)v5 + 65) < 6u )
    goto LABEL_8;
  v6 = 1;
LABEL_9:
  v13 = 5113;
  v14 = v6;
  v15 = "CCloudFileSystemApplier::SetSecurity";
  v16 = 0;
  Handle = 0;
  v12 = 0;
  v7 = 5116;
  if ( a2 && (LOWORD(v13) = 5116, v12 = 0, v7 = 5117, a3) )
  {
    LOWORD(v13) = 5117;
    v8 = CFspCloudFileSystemOperations::CreateFileW(a2, 0x140080u, (__int64)a3, 0, 0, 1u, 8u, &Handle);
    v12 = v8;
    v9 = 5126;
    if ( v8 < 0
      || (LOWORD(v13) = 5126,
          v10 = NtSetSecurityObject(Handle, 4u, a3),
          v8 = HRESULTFromNTSTATUS(v10),
          v12 = v8,
          v9 = 5128,
          v8 < 0) )
    {
      HIWORD(v13) = v9;
    }
    else
    {
      LOWORD(v13) = 5128;
    }
    if ( Handle )
    {
      NtClose(Handle);
      v8 = v12;
    }
  }
  else
  {
    v8 = -2147024809;
    v12 = -2147024809;
    HIWORD(v13) = v7;
  }
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180094118  mov     [rsp-8+arg_8], rbx
0x18009411d  mov     [rsp-8+arg_10], rsi
0x180094122  mov     [rsp-8+Handle], rcx
0x180094127  push    rbp
0x180094128  mov     rbp, rsp
0x18009412b  sub     rsp, 60h
0x18009412f  mov     rsi, r8
0x180094132  mov     rbx, rdx
0x180094135  lea     rcx, WPP_GLOBAL_Control
0x18009413c  mov     rax, cs:WPP_GLOBAL_Control
0x180094143  cmp     rax, rcx
0x180094146  jz      short loc_180094173
0x180094148  test    dword ptr [rax+44h], 100h
0x18009414f  jz      short loc_180094186
0x180094151  cmp     byte ptr [rax+41h], 6
0x180094155  jb      short loc_180094173
0x180094157  mov     edx, 73h ; 's'
0x18009415c  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x180094163  mov     rcx, [rax+38h]
0x180094167  call    WPP_SF_
0x18009416c  mov     rax, cs:WPP_GLOBAL_Control
0x180094173  test    dword ptr [rax+44h], 100h
0x18009417a  jz      short loc_180094186
0x18009417c  cmp     byte ptr [rax+41h], 6
0x180094180  jb      short loc_180094186
0x180094182  mov     cl, 1
0x180094184  jmp     short loc_180094188
0x180094186  xor     cl, cl
0x180094188  mov     [rbp+var_20], 0
0x18009418f  mov     [rbp+var_1C], 13F9h
0x180094196  mov     [rbp+var_18], cl
0x180094199  lea     rax, aCcloudfilesyst_62; "CCloudFileSystemApplier::SetSecurity"
0x1800941a0  mov     [rbp+var_10], rax
0x1800941a4  mov     [rbp+var_8], 0
0x1800941ac  mov     [rbp+Handle], 0
0x1800941b4  mov     eax, [rbp+var_20]
0x1800941b7  mov     [rbp+var_20], eax
0x1800941ba  mov     eax, 13FCh
0x1800941bf  test    rbx, rbx
0x1800941c2  jnz     short loc_1800941D5
0x1800941c4  mov     ebx, 80070057h
0x1800941c9  mov     [rbp+var_20], ebx
0x1800941cc  mov     word ptr [rbp+var_1C+2], ax
0x1800941d0  jmp     loc_18009428A
0x1800941d5  mov     [rbp+var_20], 0
0x1800941dc  mov     word ptr [rbp+var_1C], ax
0x1800941e0  mov     [rbp+var_20], 0
0x1800941e7  mov     eax, 13FDh
0x1800941ec  test    rsi, rsi
0x1800941ef  jz      short loc_1800941C4
0x1800941f1  mov     [rbp+var_20], 0
0x1800941f8  mov     word ptr [rbp+var_1C], ax
0x1800941fc  lea     rax, [rbp+Handle]
0x180094200  mov     [rsp+60h+var_28], rax; void **
0x180094205  mov     [rsp+60h+var_30], 8; unsigned int
0x18009420d  mov     [rsp+60h+var_38], 1; ULONG
0x180094215  mov     [rsp+60h+var_40], 0; ULONG
0x18009421d  xor     r9d, r9d; unsigned int
0x180094220  mov     edx, 140080h; DesiredAccess
0x180094225  mov     rcx, rbx; SourceString
0x180094228  call    ?CreateFileW@CFspCloudFileSystemOperations@@SAJPEBGKKKKKKPEAPEAX@Z; CFspCloudFileSystemOperations::CreateFileW(ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)
0x18009422d  mov     ebx, eax
0x18009422f  mov     [rbp+var_20], eax
0x180094232  mov     [rbp+var_20], eax
0x180094235  test    eax, eax
0x180094237  mov     eax, 1406h
0x18009423c  jns     short loc_180094244
0x18009423e  mov     word ptr [rbp+var_1C+2], ax
0x180094242  jmp     short loc_180094276
0x180094244  mov     word ptr [rbp+var_1C], ax
0x180094248  mov     r8, rsi; SecurityDescriptor
0x18009424b  mov     edx, 4; SecurityInformation
0x180094250  mov     rcx, [rbp+Handle]; Handle
0x180094254  call    cs:__imp_NtSetSecurityObject
0x18009425a  mov     ecx, eax
0x18009425c  call    HRESULTFromNTSTATUS
0x180094261  mov     ebx, eax
0x180094263  mov     [rbp+var_20], eax
0x180094266  mov     [rbp+var_20], eax
0x180094269  test    eax, eax
0x18009426b  mov     eax, 1408h
0x180094270  js      short loc_18009423E
0x180094272  mov     word ptr [rbp+var_1C], ax
0x180094276  cmp     [rbp+Handle], 0
0x18009427b  jz      short loc_18009428A
0x18009427d  mov     rcx, [rbp+Handle]; Handle
0x180094281  call    cs:__imp_NtClose
0x180094287  mov     ebx, [rbp+var_20]
0x18009428a  lea     rcx, [rbp+var_20]; this
0x18009428e  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180094293  mov     eax, ebx
0x180094295  lea     r11, [rsp+60h+var_s0]
0x18009429a  mov     rbx, [r11+18h]
0x18009429e  mov     rsi, [r11+20h]
0x1800942a2  mov     rsp, r11
0x1800942a5  pop     rbp
0x1800942a6  retn
```
