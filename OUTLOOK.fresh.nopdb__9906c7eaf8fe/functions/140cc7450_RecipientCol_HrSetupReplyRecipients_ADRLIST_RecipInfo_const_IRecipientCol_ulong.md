# RecipientCol::HrSetupReplyRecipients(_ADRLIST *,RecipInfo const *,IRecipientCol *,ulong)

- ea: `0x140cc7450`
- end: `0x140cc7db4`
- name: `?HrSetupReplyRecipients@RecipientCol@@UEAAJPEAU_ADRLIST@@PEBURecipInfo@@PEAUIRecipientCol@@K@Z`
- size: `2404`
- prototype: `int(RecipientCol *__hidden this, struct _ADRLIST *, const struct RecipInfo *, struct IRecipientCol *, unsigned int)`
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140031848`
- `0x14003fe90`
- `0x1400a045c`
- `0x1400dd680`
- `0x1400dd710`
- `0x1400ec6f0`
- `0x140110c1c`
- `0x1401c7b50`
- `0x140219778`
- `0x14028909c`
- `0x140503f00`
- `0x14062b77c`
- `0x1406ae340`
- `0x1407e99f0`
- `0x1407ecf10`
- `0x140cc7450`
- `0x140cd0230`
- `0x140e5dcf0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140cc7ba6`
- `KERNEL32!CompareStringW` at `0x140cc7be8`
- `KERNEL32!CompareStringW` at `0x140cc7ba6`
- `KERNEL32!CompareStringW` at `0x140cc7be8`
- `OLMAPI32!FIsFeatureEnabled` at `0x140cc7503`
- `OLMAPI32!FIsFeatureEnabled` at `0x140cc7503`
- `OLMAPI32!EtwTraceErrorTag` at `0x140cc7565`
- `OLMAPI32!EtwTraceErrorTag` at `0x140cc75be`
- `OLMAPI32!EtwTraceErrorTag` at `0x140cc7565`
- `OLMAPI32!EtwTraceErrorTag` at `0x140cc75be`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x140cc7a69`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x140cc7a73`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x140cc7a7d`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x140cc7a87`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x140cc7a69`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x140cc7a73`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x140cc7a7d`
- `OLMAPI32!__imp_MAPIFreeBuffer` at `0x140cc7a87`
- `OLMAPI32!__imp_HrGetOneProp` at `0x140cc768a`
- `OLMAPI32!__imp_HrGetOneProp` at `0x140cc76c5`
- `OLMAPI32!__imp_HrGetOneProp` at `0x140cc7700`
- `OLMAPI32!__imp_HrGetOneProp` at `0x140cc773b`
- `OLMAPI32!__imp_HrGetOneProp` at `0x140cc768a`
- `OLMAPI32!__imp_HrGetOneProp` at `0x140cc76c5`
- `OLMAPI32!__imp_HrGetOneProp` at `0x140cc7700`
- `OLMAPI32!__imp_HrGetOneProp` at `0x140cc773b`
- `OLMAPI32!__imp_PpropFindProp` at `0x140cc77d9`
- `OLMAPI32!__imp_PpropFindProp` at `0x140cc780e`
- `OLMAPI32!__imp_PpropFindProp` at `0x140cc7835`
- `OLMAPI32!__imp_PpropFindProp` at `0x140cc77d9`
- `OLMAPI32!__imp_PpropFindProp` at `0x140cc780e`
- `OLMAPI32!__imp_PpropFindProp` at `0x140cc7835`
- `Mso98Win32Client!__imp_?HrGetProp@CAcctVariant@@QEAAJPEAUIOlkAccount@@K@Z` at `0x140cc7627`
- `Mso98Win32Client!__imp_?HrGetProp@CAcctVariant@@QEAAJPEAUIOlkAccount@@K@Z` at `0x140cc7627`
- `Mso98Win32Client!__imp_??1CAcctVariant@@QEAA@XZ` at `0x140cc75c8`
- `Mso98Win32Client!__imp_??1CAcctVariant@@QEAA@XZ` at `0x140cc775a`
- `Mso98Win32Client!__imp_??1CAcctVariant@@QEAA@XZ` at `0x140cc75c8`
- `Mso98Win32Client!__imp_??1CAcctVariant@@QEAA@XZ` at `0x140cc775a`
- `Mso98Win32Client!__imp_??0CAcctVariant@@QEAA@XZ` at `0x140cc7583`
- `Mso98Win32Client!__imp_??0CAcctVariant@@QEAA@XZ` at `0x140cc7583`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc788d`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc78c3`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7913`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7945`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7b58`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7cbb`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7ce5`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7d16`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7d3b`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc788d`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc78c3`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7913`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7945`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7b58`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7cbb`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7ce5`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7d16`
- `Mso98Win32Client!__imp_?PmvalFindFromPmrow@@YAPEAU_SPropValue@@PEBU_SRow@@KHHPEAKH@Z` at `0x140cc7d3b`

## pseudocode

```c

```
