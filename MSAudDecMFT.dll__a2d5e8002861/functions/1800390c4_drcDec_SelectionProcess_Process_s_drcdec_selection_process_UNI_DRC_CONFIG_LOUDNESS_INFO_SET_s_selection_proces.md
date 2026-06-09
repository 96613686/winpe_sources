# drcDec_SelectionProcess_Process(s_drcdec_selection_process *,UNI_DRC_CONFIG *,LOUDNESS_INFO_SET *,s_selection_process_output *)

- ea: `0x1800390c4`
- end: `0x180039255`
- name: `?drcDec_SelectionProcess_Process@@YA?AW4DRCDEC_SELECTION_PROCESS_RETURN@@PEAUs_drcdec_selection_process@@PEAUUNI_DRC_CONFIG@@PEAULOUDNESS_INFO_SET@@PEAUs_selection_process_output@@@Z`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180038ed4`

## callees

- `0x1800390c4`
- `0x18003925c`
- `0x180039570`
- `0x180039788`
- `0x1800398bc`
- `0x180039d3c`
- `0x180039e7c`
- `0x18003a4d8`
- `0x18003af64`
- `0x180075128`

## pseudocode

```c
__int64 __fastcall drcDec_SelectionProcess_Process(unsigned int *a1, __int64 a2, __int64 a3, __int64 a4)
{
  _BYTE *v8; // rax
  _BYTE *v9; // rcx
  _BYTE *v10; // rdi
  __int64 result; // rax
  int v12; // ecx
  _BYTE *v13; // rbx
  _BYTE *v14; // r14
  __int64 v15; // r8
  _BYTE *v16; // rdx
  _BYTE *v17; // r13
  _QWORD v18[3]; // [rsp+30h] [rbp-18h] BYREF
  _BYTE *v19; // [rsp+90h] [rbp+48h] BYREF

  if ( !a1 )
    return 4294965298LL;
  v8 = a1 + 142;
  v9 = a1 + 258;
  v19 = v8;
  v18[0] = v9;
  if ( *v8 )
    *v8 = 0;
  if ( *v9 )
    *v9 = 0;
  v10 = a1 + 1;
  result = generateVirtualDrcSets(a1 + 1, a2, *a1);
  if ( !(_DWORD)result )
  {
    v12 = *(unsigned __int8 *)(a2 + 17);
    if ( (char)*v10 != v12 )
      *v10 = v12;
    if ( !a1[2] && *((_BYTE *)a1 + 12) || (result = channelLayoutToDownmixIdMapping(a1 + 1, a2), (int)result >= -1000) )
    {
      result = drcSetPreSelection(a1 + 1, a2, a3, v18, &v19);
      if ( !(_DWORD)result )
      {
        if ( *((_BYTE *)a1 + 44) )
        {
          v13 = (_BYTE *)v18[0];
          v14 = v19;
          v15 = v18[0];
          v16 = v19;
          v17 = v19;
          *(_BYTE *)v18[0] = 0;
          result = selectAlbumLoudness(a3, v16, v15);
          if ( (_DWORD)result )
            return result;
          if ( !*v13 )
          {
            v14 = v13;
            v13 = v17;
          }
        }
        else
        {
          v13 = v19;
          v14 = (_BYTE *)v18[0];
        }
        v18[0] = v13;
        v19 = v14;
        *v14 = 0;
        result = drcSetRequestSelection((_DWORD)v10, a2, a3, (unsigned int)v18, (__int64)&v19);
        if ( !(_DWORD)result )
        {
          result = drcSetFinalSelection(v10, v18, &v19);
          if ( !(_DWORD)result )
          {
            result = generateOutputInfo(v10, a4, a2, a3, v19 + 8);
            if ( (int)result >= -1000 )
            {
              addVirtualDrcSet(a4, a2);
              return selectDownmixMatrix(a4, a2);
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800390c4  push    rbp
0x1800390c6  push    rbx
0x1800390c7  push    rsi
0x1800390c8  push    rdi
0x1800390c9  push    r12
0x1800390cb  push    r13
0x1800390cd  push    r14
0x1800390cf  push    r15
0x1800390d1  mov     rbp, rsp
0x1800390d4  sub     rsp, 48h
0x1800390d8  xor     r13d, r13d
0x1800390db  mov     r15, r9
0x1800390de  mov     r12, r8
0x1800390e1  mov     rsi, rdx
0x1800390e4  mov     rbx, rcx
0x1800390e7  test    rcx, rcx
0x1800390ea  jz      loc_18003921C
0x1800390f0  lea     rax, [rcx+238h]
0x1800390f7  lea     rcx, [rax+1D0h]
0x1800390fe  mov     [rbp+arg_0], rax
0x180039102  mov     [rbp+var_18], rcx
0x180039106  cmp     [rax], r13b
0x180039109  jbe     short loc_18003910E
0x18003910b  mov     [rax], r13b
0x18003910e  cmp     [rcx], r13b
0x180039111  jbe     short loc_180039116
0x180039113  mov     [rcx], r13b
0x180039116  mov     r8d, [rbx]
0x180039119  lea     rdi, [rbx+4]
0x18003911d  mov     rcx, rdi
0x180039120  call    _generateVirtualDrcSets
0x180039125  test    eax, eax
0x180039127  jnz     loc_18003920A
0x18003912d  movzx   ecx, byte ptr [rsi+11h]
0x180039131  movsx   eax, byte ptr [rdi]
0x180039134  cmp     eax, ecx
0x180039136  jz      short loc_18003913A
0x180039138  mov     [rdi], cl
0x18003913a  cmp     [rbx+8], r13d
0x18003913e  jnz     short loc_180039146
0x180039140  cmp     [rbx+0Ch], r13b
0x180039144  jnz     short loc_18003915C
0x180039146  mov     rdx, rsi
0x180039149  mov     rcx, rdi
0x18003914c  call    _channelLayoutToDownmixIdMapping
0x180039151  cmp     eax, 0FFFFFC18h
0x180039156  jl      loc_18003920A
0x18003915c  lea     rax, [rbp+arg_0]
0x180039160  mov     r8, r12
0x180039163  lea     r9, [rbp+var_18]
0x180039167  mov     [rsp+48h+var_28], rax
0x18003916c  mov     rdx, rsi
0x18003916f  mov     rcx, rdi
0x180039172  call    _drcSetPreSelection
0x180039177  test    eax, eax
0x180039179  jnz     loc_18003920A
0x18003917f  cmp     [rbx+2Ch], r13b
0x180039183  jnz     loc_180039223
0x180039189  mov     rbx, [rbp+arg_0]
0x18003918d  mov     r14, [rbp+var_18]
0x180039191  lea     rax, [rbp+arg_0]
0x180039195  mov     [rbp+var_18], rbx
0x180039199  lea     r9, [rbp+var_18]
0x18003919d  mov     [rsp+48h+var_28], rax
0x1800391a2  mov     r8, r12
0x1800391a5  mov     [rbp+arg_0], r14
0x1800391a9  mov     rdx, rsi
0x1800391ac  mov     [r14], r13b
0x1800391af  mov     rcx, rdi
0x1800391b2  call    _drcSetRequestSelection
0x1800391b7  test    eax, eax
0x1800391b9  jnz     short loc_18003920A
0x1800391bb  lea     r8, [rbp+arg_0]
0x1800391bf  mov     rcx, rdi
0x1800391c2  lea     rdx, [rbp+var_18]
0x1800391c6  call    _drcSetFinalSelection
0x1800391cb  test    eax, eax
0x1800391cd  jnz     short loc_18003920A
0x1800391cf  mov     rax, [rbp+arg_0]
0x1800391d3  mov     r9, r12
0x1800391d6  add     rax, 8
0x1800391da  mov     r8, rsi
0x1800391dd  mov     rdx, r15
0x1800391e0  mov     [rsp+48h+var_28], rax
0x1800391e5  mov     rcx, rdi
0x1800391e8  call    _generateOutputInfo
0x1800391ed  cmp     eax, 0FFFFFC18h
0x1800391f2  jl      short loc_18003920A
0x1800391f4  mov     rdx, rsi
0x1800391f7  mov     rcx, r15
0x1800391fa  call    _addVirtualDrcSet
0x1800391ff  mov     rdx, rsi
0x180039202  mov     rcx, r15
0x180039205  call    _selectDownmixMatrix
0x18003920a  add     rsp, 48h
0x18003920e  pop     r15
0x180039210  pop     r14
0x180039212  pop     r13
0x180039214  pop     r12
0x180039216  pop     rdi
0x180039217  pop     rsi
0x180039218  pop     rbx
0x180039219  pop     rbp
0x18003921a  retn
0x18003921c  mov     eax, 0FFFFF832h
0x180039221  jmp     short loc_18003920A
0x180039223  mov     rbx, [rbp+var_18]
0x180039227  mov     rcx, r12
0x18003922a  mov     r14, [rbp+arg_0]
0x18003922e  mov     r8, rbx
0x180039231  mov     rdx, r14
0x180039234  mov     r13, r14
0x180039237  mov     byte ptr [rbx], 0
0x18003923a  call    _selectAlbumLoudness
0x18003923f  test    eax, eax
0x180039241  jnz     short loc_18003920A
0x180039243  cmp     [rbx], al
0x180039245  jnz     short loc_18003924D
0x180039247  mov     r14, rbx
0x18003924a  mov     rbx, r13
0x18003924d  xor     r13d, r13d
0x180039250  jmp     loc_180039191
```
